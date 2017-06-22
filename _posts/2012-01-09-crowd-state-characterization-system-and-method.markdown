---

title: Crowd state characterization system and method
abstract: A crowd state characterization system utilizes a plurality of processors to analyze video streams from numerous videos to select videos and/or video frames of interest. The processors digitize dismounts such as pedestrians and the like and then analyze the digitized pedestrians. The frames of video are characterized in terms of entropy related to discordant motion and enthalpy related to energy. A selector can then select from among numerous videos to allow observation of videos numerically determined to be of interest.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09208386&OS=09208386&RS=09208386
owner: The United States of America as represented by the Secretary of the Navy
number: 09208386
owner_city: Washington
owner_country: US
publication_date: 20120109
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefore.

The present invention relates generally to crowd surveillance and more specifically to an automated crowd surveillance system that mitigates information overload by producing metrics related to the underlying crowd sociology.

Prior art crowd surveillance uses several monitor banks and human monitors to switch video feed to camera sites which are too numerous to display at one time. With hundreds or thousands of displays available command centers cannot effectively discriminate between benign dangerous and anomalous crowd situations. Automated pedestrian and vehicle detection systems simply produce a sequence of maps of the detected pedestrians and vehicles at particular time frames.

The prior art does not show the features of the present invention which reduces the megapixel images in video frames to a few variables relevant to the state of the crowd and automatically directs operators to the particular cameras which may be of interest from the numerous available camera feeds available. Accordingly those of skill in the art will appreciate the present invention which addresses the above discussed problems.

Another possible object of the present invention is to provide a system that mitigates information overload for operators who manage crowd surveillance.

Another possible object of the invention is to provide a crowd surveillance system that can detect rapid changes in crowd behavior.

Another possible object of the invention is to provide a crowd surveillance system that requires less storage space than previous systems.

Other objects and advantages of the present invention will become apparent from the following descriptions taken in connection with the accompanying drawings wherein by way of illustration and example an embodiment of the present invention is disclosed. However it will be understood that the present invention is not limited to the above and or other objects of the invention.

In accordance with the present invention a system is provided for automatically characterizing a plurality of video streams. The present invention may comprise elements such as but not limited to a plurality of cameras that produce a plurality of video streams and a plurality of processors such as ASIC s for receiving the plurality of video streams each video stream comprising frames of video.

Each of the plurality of processors for example Field Programmable Gated Arrays FPGAs is programmed for digitizing a plurality of dismounts within the video streams and producing numerical characterizations for the digitized dismounts. The numerical characterizations represent an enthalpy related to an energy of the dismounts and entropy related to a discordance of motion of the dismounts with respect to a comparison of the frames of video where the video streams are numerically characterized using both the enthalpy and entropy.

In one embodiment the plurality of processors is operable for determining crowd region of influence related to a density of the dismounts and a numerical value for a crowd temperature from the region of influence a number of the dismounts and the enthalpy and entropy.

The plurality of cameras may comprise over 50 or 100 cameras and may further comprise a selector module operable to select a particular feed of the video streams based on threshold values for the numerical characterizations for the enthalpy and entropy.

In one embodiment the processors may comprise a detector module operable for detecting and digitizing the dismounts within the video feeds and a crowd module which determines the numerical characterizations of the dismounts for the enthalpy and entropy.

In another embodiment the system may further comprise a plurality of camera housings for the cameras whereby each of the plurality of processors is mounted to respective camera housings.

The crowd state characterization system may further comprise a detector module for each of the processors wherein the detector module may comprise a training module which detects initial test dismounts in a video stream which is known to comprise few or no dismounts. The initial test dismounts are subtracted from subsequently detected dismounts before characterizing the number of dismounts for the enthalpy and entropy.

In another embodiment the present invention provides a method for automatically characterizing a plurality of video streams. Steps in the method may comprise programming multiple FPGA processors for processing a plurality of video streams wherein each of the processors are programmed for digitizing a plurality of dismounts within the video streams.

Other steps may comprise programming the processors for producing numerical characterizations for the digitized dismounts and programming the numerical characterizations to represent an enthalpy related to an energy of the dismounts and an entropy related to a discordance of motion of the dismounts with respect to a comparison of the frames of video.

In this way the frames or groups of frames of the video streams are numerically characterized for the enthalpy and entropy. The operators can select those for viewing. The method may comprise mounting the processors into a plurality of cameras that produce the video streams.

The method provides for use of a plurality of cameras which may comprise over 50 cameras and may further comprise providing a selector module operable to select a particular feed of the video streams based on a plurality of threshold values for the numerical characterizations for the enthalpy and entropy. The method may further comprise programming the processors for determining a region of influence related to a density of the dismounts and a numerical value for a crowd temperature from the size of the region of influence a number of the dismounts and the enthalpy and entropy.

The method may comprise providing that each of the processors comprise a detector module operable for detecting and digitizing the dismounts within the video feeds and a crowd module which determines the numerical characterizations of the dismounts for the enthalpy and entropy.

The method may further comprise providing a detector module for each of the processors wherein the detector module may comprise a training module which detects initial test dismounts in a video which are known to comprise few or no actual dismounts whereupon the initial test dismounts are subtracted from subsequently detected dismounts.

Detailed descriptions of the preferred embodiment are provided herein. It is to be understood however that the present invention may be embodied in various forms. Therefore specific details disclosed herein are not to be interpreted as limiting but rather as a basis for the claims and as a representative basis for teaching one skilled in the art to employ the present invention in virtually any appropriately detailed system structure or manner.

The present invention may be utilized to sort through numerous or large numbers of video streams to detect anomalous crowd behavior. By large numbers it is meant herein to be greater than 50 video streams although hundreds or thousands of video steams may be present for analysis or observation preferably in real time.

In one presently preferred embodiment the detection methods utilize hardware software components which are able to quickly characterize each frame of data by reducing the information from megabytes to a relatively small number of bytes. Software may also be utilized but may not operate as quickly. In one embodiment FPGA integrated circuits are programmed to analyze the data from a video stream in real time either at each camera or at central locations that receive the video streams. Software alone may also be utilized but may not operate as quickly.

Detection programs can be utilized to digitize vehicles pedestrians walkers runners people hiding people stationary body positions facial expressions and the relative changes of the detected movement. This is sometimes referred to by those of skill and herein as digitizing dismounts which refers to the detected pedestrians vehicles features thereof and the like. The digitization system uses the current state of the art in pedestrian detection based on variants of the AdaBoost algorithm and or the Viola Jones cascade VJ cascade .

In the first detectors of the cascade it is desirable to select all potential dismounts. It has been found that the false alarm rate is typically not small. However detection size has not been found to be a concern. Accordingly it is desirable to have small size but powerful detectors. The present system uses high probability of detection high detection power algorithms. False alarms are dealt with more effectively by exclusion in subsequent high power moderate size stages of the cascade. Initial choices for detectors include Kullback and Fisher Linear Discriminant FLD . But the choice of detector is necessarily left to the user due to advancing competing methods in the detection fields.

Once digitized thermodynamic equations may be utilized to analyze the resulting digitized detected dismounts such as pedestrians and the like in terms of crowd entropy crowd enthalpy and crowd temperature. 

For purposes of the present invention the term enthalpy is utilized to represent the sum of energy of the digitized dismounts. For example a large number of detected dismounts with faster motion would result in a higher crowd enthalpy. A smaller number of detected dismounts moving in slower motion would result in a lower enthalpy. Likewise a large number of dismounts that are relatively stationary results in a relatively lower crowd enthalpy.

While many equations could be utilized to represent the crowd enthalpy mathematically a few representative thermodynamic equations related to entropy are provided herein as non limiting examples. As well the invention may comprise equations to represent the energy in other ways that might not be classical thermodynamic equations. It will be appreciated that one of skill in the art can provide programming that detects the motion of the dismounts the speed thereof the number of dismounts and determines an overall crowd enthalpy. 

 Crowd entropy as used herein refers to the type of motion of the digitized dismounts. Very generally consistent movement of each digitized dismount and or flowing movement whereby the dismounts move relatively in the same direction results in a low crowd entropy whereas inconsistent motion and or different types of motion or direction of motions of the digitized dismounts results in higher crowd entropy. In accordance with the present invention thermodynamic equations relating to enthalpy are used as non limiting examples. However it will be understood that one of skill in the art can provide programming that analyzes the movement of the dismounts to determine regularity of movement of particular dismounts as well the degree of different movements of the dismounts to thereby provide a crowd entropy in accordance with the present invention.

The camera images can be characterized mathematically by the hardware software discussed herein based on where they are plotted on the graph. Calm and orderly images as indicated at have low entropy and low enthalpy values. For example a large crowd that is sitting in an auditorium might be classified as calm and orderly. Because the digitized dismounts do not have significant movement the energy or enthalpy is low. Likewise because the digitized dismounts are relatively organized in place in their seats the entropy would also be low.

On the other hand a digitized image of dismounts comprising a large group of people starting a marathon would result in high enthalpy due to their combined significant motion or energy. However due to relatively consistent repetitive and or flowing motion the digitized dismounts would be classified mathematically as orderly resulting in a classification of agitated and orderly as indicated at . Agitated and orderly images as might be used here as a classification have relatively low entropy values but high enthalpy value.

Agitated and disorderly 27 images have high entropy and high enthalpy values. For example relatively large numbers of digitized dismounts going quickly and irregularly in different directions with quickly varying motions of the individual digitized dismounts as may occur during a riot would result in an agitated and disorderly classification. Thus a large number of quickly moving digitized dismounts moving in relatively different directions or with discordant or uneven movements would result in this classification.

Calm and chaotic 29 images have high entropy value but low enthalpy value. For example digitized examples of a small meeting in a park breaking up where participants walk off in different directions might be characterized in this way. The relatively small group is moving rather slowly giving readings or mathematical classifications of low energy or enthalpy. However the different paths taken by the different participants may result in a relatively higher entropy.

Crowds with particular characteristics cluster into different locations on the H S plot as depicted in the graph based on these labels in accordance with one possible embodiment of the invention. In accordance with the present invention mathematical triggers or thresholds may be set e.g. enthalpy greater than 1 and entropy greater than 15 to direct attention of the human monitors to the particular video streams with such values when it is desired for example to focus on crowds more likely to be in a state of riot. The selection may by automatic where a video automatically pops up or partially automatic where the system notifies an operator who then chooses whether or not to view the video.

As well the type of crowd state for viewing may be selectable so that the thresholds for calm and orderly agitated and orderly calm and chaotic could be similarly detected with appropriate triggers. In this way numerous streams of video can be better monitored for the selected behavior of interest.

In another embodiment a crowd temperature may be calculated. The processor is programmed to detect a crowd volume or region of influence based on a selected density of digitized dropouts. For example the processor may detect a size of crowd volume or region where the density exceeds a selected value. The size of this region might then be measured. Utilizing the size or crowd volume the number of digitized dismounts the enthalpy and the entropy a crowd temperature is numerically determined. In this case use of a thermodynamic entropy Gibb s entropy may model sociology better and more theoretically consistently but an information entropy Shannon s entropy may be adequate for crowd classification. Either entropy may be programmed by the user with algorithms of their choice to exploit advances in computation. Thus frames of a video stream may be characterized by a relatively small amount of information e.g. the crowd temperature entropy and enthalpy. In terms of bytes this can be expressed with greatly reduced bandwidth.

An enlarged internal camera construction shows a representative block diagram for a typical camera as used herein. Camera construction may comprise a circuit board which electrically connects with an imaging sensor which could be a charge coupled device or CCD that electronically captures image in terms of frames of a video stream. CCD may transmit image to memory unit and or provide camera output video frames of image which the camera captured. CCD also feeds image to a Field Programmable Gated Array processor FPGA in accordance with the present invention. It will be noted that the FPGA may be located at different location than the camera but in this example the FPGA is located at the camera to analyze the raw data. The FPGA is programmed to analyze the video stream to characterize the crowd in the manner discussed above. However it will be appreciated that software analysis may also be provided if desired. Generally specifically designed hardware operates much faster than software.

Accordingly the FPGA may be a form of application specific integrated circuit ASIC that is programmed to replace frames of video from image with three values entropy enthalpy and temperature. These values may then be stored in second memory unit of the camera and or output as crowd data .

Selector may be utilized to compare the crowd data to select a particular video stream and or selected crowd data in accordance with one possible embodiment of the invention based on the desired threshold levels for entropy enthalpy and or temperature as discussed above. In this way it is possible for a limited number of operators to manage a large number of video streams.

The Viola Jones cascade is a state of the art algorithm in pedestrian or dismount detection. In the first detector of the cascade detection size is not as significant a concern as that of making sure to select all potential dismounts. False alarms such as mechanical movement are dealt with more effectively by exclusion in subsequent high power moderate size stages of the cascade. Possible detectors include Kullback and Fisher Linear Discriminant FLD based on their proven ability for pedestrian facial and vehicle detection and location in accordance with one possible embodiment of the invention.

During step the location image is processed to provide the overall energy and direction of motion of the digitized dismounts. In this step binary images are processed and used to calculate the enthalpy H and entropy S values which are two presently preferred basic parameters for the model.

In one embodiment a free energy choice of enthalpy is a speed of calculation choice where mechanical interaction is accounted for in the method by multiplying the volume V times the sensitivity of the average and fluctuation internal energy uand u to changes in volume.

In one possible embodiment enthalpy might be calculated by multiplying the crowd mass m times the following equation 

The enthalpy H and entropy S values are then analyzed to determine the behavioral state of the crowd.

In step a comparison of the H S state to benign danger boundary is conducted. The enthalpy entropy state provides a metric to be used where a set of approved or benign states are defined in the system analysis as well as a set of danger states. In analogy to estimation theory the map of these states provides the basis vectors for a support vector machine SVM to define the boundary of operation using theoretically clean methods from learning theory. These values are used to decide if the crowd behavior is benign anomalous or changing dangerously.

Those with skill in the art will appreciate the invention as improving upon previous crowd surveillance methods that used several monitor banks and a human monitor to switch video feed to camera sites which were too numerous to display at one time. Even if thousands of displays were available command centers could not effectively disseminate all the images to determine the crowd s current behavior and if that behavior was soon to change.

Enthalpy and entropy values are utilized in step to determine a crowd temperature. Crowd temperature T is determined from the assumed region of influence crowd fluid volume density or number of dismounts and enthalpy H and entropy S values. In deriving crowd temperature the sociological nature of the crowd is measured. This crowd temperature which is more than physical velocity is of use to sociological studies and more accurately provides a measure of crowd temperature than using the specific internal energy represented by the equation U v v 2 2.

 Specific indicates a value is in terms of per unit mass used here to avoid direct use of inertial effects that resist motion of the crowd. Variable symbols for specific quantities are shown as the lower case letter of the non specific full quantity. For example specific crowd enthalpy is h H m. The crowd mass m is necessarily different from the physical dismount masses in order to take sociological and socio psychological effects on their physical velocities into account.

In this embodiment the crowd temperature provides a convenient metric with a simple hot cold perception. In combination with other crowd state metrics the crowd temperature provides a feature fusion capability in accordance with one possible embodiment of the invention.

In step a crowd temperature is determined as discussed above. In step non ideal nonlinear values are calculated to be used in analysis of crowd data from . The final two steps and involve correcting the first virial and then determining a critical crowd temperature .

A useful feature of the present invention is that the enthalpy the entropy and the crowd temperatures are three floating point numbers with orders of magnitude requiring less data storage space than even compressed full video streams. Typical data sizes would be 6 to 12 bytes compared with megapixel images that change every with every unit time step. Therefore the status of more image streams is stored in memory from which the method can analyze images and determine the behavioral state of the crowd as the crowd changes in time.

Crowd temperature or thermo measure is then computed from entropy and enthalpy values and stored. Plot entropy enthalpy module plots the image values on a graph based on metric histories of crowds as discussed hereinbefore in connection with . Reports derived from such analysis advises a user on the behavioral state of the crowd as compared to other crowd states in accordance with one possible embodiment of the invention.

During training for example a video of an area at a time it is known to be empty without dismounts may be utilized wherein any detected dismounts would be false. Thus these could be eliminated. Likewise known pedestrians could be utilized for training purposes.

Module transmits filters to module for detecting pedestrians used to calculate crowd parameters in module of . Filters are representative of detected pedestrians. This module filters out parts of the image irrelevant in determining crowd behavior as discussed hereinbefore.

Common filters may be represented mathematically as hj hk hl hm hn and ho. Filter features are processed through module for correcting feature selections which are then sent to training filter . Module is used to choose training filters and outputs detection features in accordance with one possible embodiment of the invention.

Pedestrian frame value is sent to module to calculate frame spatial correlation which then determines pedestrian entropy and forwards this data to temp video and then to next step in the baseline method. Pedestrian frame value and raw video are processed through dynamics buffer en route to substep module to calculate frame temporal correlation. Module determines pedestrian enthalpy and also transmits pedestrian frame and pedestrian velocities values to module which detects motion. Module transmits temporary video and found pedestrians back to module cascade detectors which reiterates the operation in accordance with one possible embodiment of the invention.

Module also forwards trained features to module which provides cascade pedestrian detectors. Raw video is transmitted from module to module to check counts and normalize this information.

Module and module then exchange information to be used in their respective functions pedestrian frame value is sent to module while counts value is sent to module . Module then determines pedestrian frame value which passes through dynamics buffer which tracks the pedestrian location in time before sending said value on to module . Module sends found pedestrians and temp video values on to module where values are determined by using Classic Viola Jones algorithm in accordance with one possible embodiment of the invention. Other possible embodiments of the invention could use Multiple Instance Learners algorithms such as MlLboost or Noisy OR.

In another embodiment if the cameras were focused on facial expressions and the facial expressions were moving quickly for example laughing at a joke the associated frames of a sitting crowd might be characterized as having high enthalpy and entropy. Accordingly the invention may be utilized to classify crowds for purposes that may not be associated with extreme behavior but rather variations of normal behavior.

It will be understood that many additional changes in the details materials steps and arrangement of parts which have been herein described and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

The foregoing description of the preferred embodiments of the invention has been presented for purposes of illustration and description only. It is not intended to be exhaustive nor to limit the invention to the precise form disclosed and obviously many modifications and variations are possible in light of the above teaching. Such modifications and variations that may be apparent to a person skilled in the art are intended to be included within the scope of this invention as defined by the accompanying claims.

