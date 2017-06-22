---

title: Correlation image detection
abstract: A correlation image detection method is provided that co-registers sonar images by finding peaks in correlation images. To obtain the peaks, the mean of the absolute values of the correlation coefficients in the correlation image is found and the Rayleigh parameter is determined from the mean. Based on the Rayleigh parameter, an appropriate threshold can be determined using a desired probability of false detection. The threshold can be chosen such that the probability of a single false detection over the expected life of the mission for which correlation detection is being performed is extremely low. The peak value in the image is determined and a correlation is considered detected when the peak value is greater than the product of the threshold and the Rayleigh parameter. If a detection occurs, the correlation image detector returns the transformation that co-registers the two images.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08594457&OS=08594457&RS=08594457
owner: The United States of America as represented by the Secretary of the Navy
number: 08594457
owner_city: Washington
owner_country: US
publication_date: 20120607
---
This is a divisional application claiming the benefit of parent application Ser. No. 12 454 484 filed on May 18 2009 now U.S. Pat. No. 8 326 081 the entire disclosure of which is incorporated hereby by reference. This patent application is related to co pending patent applications entitled COMPENSATING SONAR IMAGES FOR DIFFERENCES IN TARGET ASPECT Ser. No. 12 802 453 filed May 17 2010 COHERENT IMAGE CORRELATION Ser. No. 12 454 485 filed May 18 2009 GRAZING ANGLE COMPENSATION Ser. No. 12 802 454 filed May 17 2010 and SPATIALLY INVARIANT IMAGE FORMATION USING OPEN AND CLOSED APERTURES Ser. No. 12 454 486 filed May 18 2009 all these co pending applications being by the same inventor as this application.

The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

The present invention relates to correlation of sonar images and more specifically to finding peaks in correlation images to co register sonar images using a threshold based on a statistical model and a desired probability of false detections.

As is known in the art there are many applications for which it is necessary to determine the relationship between two images. As an example forming enhanced apertures according to the open closed aperture theorem such as combining grid lines to create circular Synthetic Aperture Sonar SAS like images requires one to co register images created during different survey legs or by different robots.

Also when navigating using a Kalman filter the relationship between two images can be compared to a predicted relationship and the difference can be used to improve the state estimate. In addition when mosaicking the relationship between images can be used to stitch images together and generate a single larger image. Still further when searching for targets it is desirable to know that there are targets in an image and to know where they are.

When correlating two sonar images it is often necessary to determine whether or not the images are of the same object or terrain and the relative position and orientation of one image with respect to the other. This can require choosing a peak in the correlation image and determining whether its value is significant. For navigational algorithms it is often desirable to use a detection criterion with a low false alarm rate.

However the correlation coefficients in a correlation image are difficult to predict as they depend on the amount of structure being imaged the background noise in the environment and the degree of frequency and aspect overlap. What are needed are systems and methods for detecting correlation in images.

It is therefore a general purpose and primary object of the present invention to provide a correlation image detector wherein sonar images are co registered by finding peaks in correlation images. The peaks are found using a threshold based on a statistical model and a desired probability of false detections. The threshold can be chosen such that the probability of a single false detection over the expected life of the mission for which correlation detection is being performed is extremely low e.g. one in a million.

To obtain the peaks the mean of the absolute values of the correlation coefficients in the correlation image is found. As is known in the art and described in further detail hereinafter the image background follows a Rayleigh distribution. Accordingly the Rayleigh parameter can be determined from the mean. Based on the Rayleigh parameter an appropriate threshold can be determined using a desired false detection probability.

The peak value in the image is compared to the product of the threshold and the Rayleigh parameter. A correlation is considered detected when the peak value is greater than the product. If a detection occurs the correlation image detector returns the transformation that co registers the two images which can include translations and rotations.

In one embodiment a correlation image detector comprises the steps of obtaining a mean of absolute values of correlation coefficients in a correlation image determining a Rayleigh parameter from the mean determining a threshold value based on a desired false detection probability and registering a detection if a peak one of the correlation coefficients exceeds a product of the threshold and the Rayleigh parameter.

In another embodiment the correlation image detector further comprises correlating a plurality of coherent sonar images to obtain the correlation image wherein the correlation image comprises a matrix showing correlation coefficients vs. spatial translation or spatial translation and rotations.

In another embodiment the correlation image detector further comprises obtaining from the correlation image the spatial translation and or spatial translation and rotations corresponding to the peak.

In another embodiment the plurality of correlation images comprises a set of correlation images each image of said set corresponding to a different rotation and registering a detection further comprises determining if the peak one of the correlation coefficients exceeds a stored peak replacing the stored peak with the peak one when the peak one exceeds the stored peak and returning to obtaining a mean for a next one of set wherein upon completing the set the rotation corresponding to the stored peak is a preferred rotation.

On one embodiment a correlation image detector comprises the steps of correlating a plurality of coherent sonar images to obtain a correlation image wherein the correlation image comprises a matrix showing correlation coefficients vs. spatial translation or spatial translation and rotations obtaining a mean T of absolute values of the correlation coefficients in the correlation image from the relationship

As previously described herein the correlation coefficients in a correlation image are difficult to predict as they depend on the amount of structure being imaged the background noise in the environment and the degree of frequency and aspect overlap. To understand correlation image detection it is helpful to decompose the image into two parts the peak and the background noise.

The peak corresponds to the correct co registration and only occurs if images overlap. The background noise occurs in all correlation images and corresponds to incorrect co registrations. The number of pixels composing the peak is often small. On the other hand the number of pixels that contain only noise is very large. In a typical image having millions of pixels the peak including sidelobes may be fewer than 50 pixels while those containing only noise may be on the order of millions of pixels.

As a consequence even in images with strong peaks it is usually possible to calculate the statistics of the noise simply by calculating statistics for the entire image. The pixels corresponding to the peak are usually so few that they fail to significantly bias the noise statistics. However the signal to noise ratio is often very good.

Referring now to there is shown scatter plot of the complex correlation coefficients corresponding to the correlation of two non overlapping images. Referring also to there is shown a plot of the absolute value of the correlation coefficients for the data of .

Those of skill in the art will recognize that plot corresponds well with a theoretical Rayleigh distribution. Accordingly both scatter plot and plot are normalized by the Rayleigh parameter 

The x and y axes in respectively correspond to the real and imaginary parts of the correlation coefficients in the image. Scatter plot includes roughly three million points. As shown in scatter plot the data all lies within 6 Rayleigh parameters of zero.

By comparison illustrates a scatter plot of the complex correlation coefficients corresponding to the correlation of two images of the same topographical area. Being of the same topographical area the images are correlated and there is a peak in the correlation which greatly exceeds the magnitude of the noise.

Scatter plot shows approximately the same number of data points as shown in with roughly three million points about 0 0 . However 50 or so outliers are somewhat distant from the center gathering. For clarity of illustration only a limited number of outliers are designated in . Outliers are due to the peak in the correlation and allow for robust detection since they are highly unlikely based on the statistics of the noise distribution.

Referring now to there is shown a block diagram of a method for correlation image detection. At block coherent sonar images are correlated to obtain an M N correlation image showing correlation coefficient vs. translation. Block obtains the mean of the absolute values of the correlation coefficients i j in the correlation image of block where

At block a threshold T is determined based on the desired false detection probability. The probability that the peak value of the correlation coefficients is greater than the product of the threshold and the Rayleigh parameter is determined by the relationship

Block compares the peak correlation coefficient value of the image to the product Ts. If Ts then a correlation is deemed detected. Upon detection block uses the peak value in the correlation image to obtain the corresponding translational relationship between the two coherent sonar images. If further images are to be processed as determined at block method returns to block .

What has thus been described is a correlation image detector that finds peaks in correlation images to co register sonar images using a threshold based on a statistical model and a desired probability of false detections. Coherent images are correlated to obtain a correlation image. The mean of the absolute values of the correlation coefficients is used to obtain the Rayleigh parameter. A false detection threshold value is determined based on a desired probability of false detections.

A correlation is detected if the absolute value of one or more correlation coefficients is greater than the product of the Rayleigh parameter and the threshold value. The translational relationship of the coherent images corresponding to the peak correlation coefficients are obtained from the correlation image.

Obviously many modifications and variations of the present invention may become apparent in light of the above teachings. For example the method can be applied to radar imagery as well sonar imagery. Additionally the correlation image may be in the form of a multi dimensional matrix showing correlation vs. spatial translation and rotations.

In this case there can be a set of correlation images corresponding to different rotations. Referring again to there are shown in phantom blocks and for determining the peak correlation value for the set of correlation images.

At block the current peak value is compared to a stored peak value. In the first iteration of method the stored peak value would be null. If the current peak is greater than the stored peak as determined at block the current peak then becomes the stored peak at block and method continues as before. The relationships obtained at block now include translational and rotational relationships of the coherent images corresponding to the peak correlation coefficients.

It will be understood that many additional changes in details and arrangements of diagrams which have been described herein and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

