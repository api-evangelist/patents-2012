---

title: Method and system for providing stimulation inputs to a visual prosthesis implant
abstract: Stimulation inputs are provided to a visual prosthesis implant. The images captured by a video decoder are received and digitized to provide a plurality of video frames; integrity of the video frames is checked, the checked video frames are filtered, and the filtered video frames are converted to stimulation inputs. A similar system is also disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08620443&OS=08620443&RS=08620443
owner: Second Sight Medical Products, Inc.
number: 08620443
owner_city: Sylmar
owner_country: US
publication_date: 20120629
---
This application is a divisional application of U.S. patent application Ser. No. 12 114 557 filed May 2 2008 for Method and System for Providing Stimulation Inputs to a Visual Prosthesis now U.S. Pat. No. 8 239 035 which claims priority to U.S. Provisional Application 60 928 407 filed on May 8 2007 and U.S. Provisional Application 60 928 440 filed on May 8 2007 the contents of both of which are incorporated herein by reference in their entirety. This application may also be related to U.S. Pat. No. 7 957 811 for Spatial Mapping for a Visual Prosthesis filed May 2 2008 the contents of which are also incorporated by reference in their entirety.

This invention was made with government support under grant No. R24EY12893 01 awarded by the National Institutes of Health. The government has certain rights in the invention.

The present disclosure relates to operation of visual prostheses implants. More in particular it relates to a method and system for providing stimulation inputs to a visual prosthesis implant.

According to a first aspect a method for providing stimulation inputs to a visual prosthesis implant is provided comprising a receiving images captured by a video decoder b digitizing the images to provide a plurality of video frames c checking integrity of the video frames to provide checked video frames d filtering the checked video frames to provide filtered video frames and e converting the filtered video frames to stimulation inputs for the visual prosthesis implant.

According to a second aspect a system for providing stimulation inputs to a visual prosthesis implant is provided comprising a receiver to receive images captured by a video decoder a digitizer to digitize the received images to provide a plurality of video frames a video input handler to check integrity of the video frames to provide checked video frames a video filter processor to filter the checked video frames to provide filtered video frames and a telemetry engine video manager to convert the filtered video frames to stimulation inputs for the visual prosthesis implant.

According to another aspect of the present disclosure an improved method is provided where a visual prosthesis is operated by way of downloadable stimulation maps to control neural stimulation based on a predetermined best fit for an individual patient.

Further aspects of the present disclosure are provide in the written specification drawings and claims of the present application.

A Retinal Stimulation System disclosed in U.S. application Ser. No. 11 207 644 filed Aug. 19 2005 for Flexible Circuit Electrode Array by Robert J. Greenberg et al. incorporated herein by reference is intended for use in subjects with retinitis pigmentosa. and show a Retinal Stimulation System wherein a patient subject is implanted with a visual prosthesis. Reference can also be made to FIGS. 1 5 of U.S. application Ser. No. 11 796 425 filed Apr. 27 2007 for Visual Prosthesis Fitting also incorporated herein by reference in its entirety.

The Retinal Stimulation System is an implantable electronic device containing electrode array that is electrically coupled by a cable that pierces sclera of the subject s eye and is electrically coupled to an electronics package external to the sclera. The Retinal Stimulation System is designed to elicit visual percepts in blind subjects with retinitis pigmentosa.

Referring to a Fitting System FS may be used to configure and optimize the visual prosthesis of the Retinal Stimulation System .

The Fitting System may comprise custom software with a graphical user interface GUI running on a dedicated laptop computer . Within the Fitting System are modules for performing diagnostic checks of the implant loading and executing video configuration files viewing electrode voltage waveforms and aiding in conducting psychophysical experiments. A video module can be used to download a video configuration file to a Video Processing Unit VPU and store it in non volatile memory to control various aspects of video configuration e.g. the spatial relationship between the video input and the electrodes. The software can also load a previously used video configuration file from the VPU for adjustment.

The Fitting System can be connected to the Psychophysical Test System PTS located for example on a dedicated laptop in order to run psychophysical experiments. In psychophysics mode the Fitting System enables individual electrode control permitting clinicians to construct test stimuli with control over current amplitude pulse width and frequency of the stimulation. In addition the psychophysics module allows the clinician to record subject responses. The PTS may include a collection of standard psychophysics experiments developed using for example MATLAB MathWorks software and other tools to allow the clinicians to develop customized psychophysics experiment scripts.

Any time stimulation is sent to the VPU the stimulation parameters are checked to ensure that maximum charge per phase limits charge balance and power limitations are met before the test stimuli are sent to the VPU to make certain that stimulation is safe.

Using the psychophysics module important perceptual parameters such as perceptual threshold maximum comfort level and spatial location of percepts may be reliably measured.

Based on these perceptual parameters the fitting software enables custom configuration of the transformation between video image and spatio temporal electrode stimulation parameters in an effort to optimize the effectiveness of the retinal prosthesis for each subject.

The Fitting System laptop is connected to the VPU using an optically isolated serial connection adapter . Because it is optically isolated the serial connection adapter assures that no electric leakage current can flow from the Fitting System laptop .

As shown in the following components may be used with the Fitting System according to the present disclosure. A Video Processing Unit VPU for the subject being tested a Charged Battery for VPU Glasses a Fitting System FS Laptop a Psychophysical Test System PTS Laptop a PTS CD not shown a Communication Adapter CA a USB Drive Security not shown a USB Drive Transfer not shown a USB Drive Video Settings not shown a Patient Input Device RF Tablet a further Patient Input Device Jog Dial Glasses Cable CA VPU Cable CFS CA Cable CFS PTS Cable Four 4 Port USB Hub Mouse LED Test Array Archival USB Drive an Isolation Transformer not shown adapter cables not shown and an External Monitor not shown .

The external components of the Fitting System according to the present disclosure may be configured as follows. The battery is connected with the VPU . The PTS Laptop is connected to FS Laptop using the CFS PTS Cable . The PTS Laptop and FS Laptop are plugged into the Isolation Transformer not shown using the Adapter Cables not shown . The Isolation Transformer is plugged into the wall outlet. The four 4 Port USB Hub is connected to the FS laptop at the USB port. The mouse and the two Patient Input Devices and are connected to four 4 Port USB Hubs . The FS laptop is connected to the Communication Adapter CA using the CFS CA Cable . The CA is connected to the VPU using the CA VPU Cable . The Glasses are connected to the VPU using the Glasses Cable .

Video processing can be configured using a collection of settings known as video configuration information. This information can be dynamically set by the host. It includes a spatial map a brightness map timing profiles and Image Presentation Rate Stimulation Frequency and zoom settings. See also .

The spatial map is used by the video filters when processing the raw video image. The spatial map can contain one pixel location for every electrode and assume a 12 20 raw video image. A possible application programming interface API can be defined as follows 

The brightness map is used by the telemetry engine video manager later discussed to translate the filtered video image brightness levels to driver amplitude values. For each brightness level an electrode can have a unique corresponding driver amplitude value. There can be one driver amplitude range that is used for all electrodes.

According to one embodiment of the present disclosure there are six timing profiles that can be configured. Each electrode associates one of the six profiles with its anodic pulse and one of the six for its cathodic pulse.

As to the video filter settings the filter processor can be configured to perform a reverse video filter in conjunction with the DoG filter.

The Image Presentation Rate Stimulation Frequency is used to determine how often to present a new video image to the patient. The maximum effective rate can be 30 Hz if a Phillips video decoder is used as decoder . The host specifies how many frames to pad between video image frames. It can be configured for faster than 30 Hz but this means a video frame is repeated.

A video engine receives the images captured by the video decoder . The video engine comprises three components a video input handler a video filter processor and a telemetry engine video manager .

The video input handler configures the video decoder acquires a raw video input from the video decoder and verifies the integrity of the raw digitized video frame by checking for frame line headers. Once a video frame has been successfully acquired by the video input handler the frame is passed to the video filter processor . The video input handler can also be responsible for detecting a video overrun following which the system is stopped . The video input handler also deals with situations where the video engine does not complete its processing of an individual video frame before a new frame arrives.

The video filter processor receives a raw digitized video frame from the video input handler and performs filtering to produce a video output image that can be used by the telemetry engine. The video filter processor uses the spatial map configured by the host and additional filter settings to qualify its filtering decisions. In the preferred embodiment the output of the video filter processor is a 6 10 image one pixel for each electrode.

The telemetry engine video manager converts the filtered video frame output from the video filter processor into stimulation frames that are sent to the implant . The telemetry engine video manager is responsible for accomplishing the image stimulation frequency. The telemetry engine video manager is also associated to an image frequency an output current range and a brightness map .

An application programming interface API for establishing communication between the three parts of the video engine will now be described.

Purpose the video input handler calls this function to invoke the video filter processor . The video output frame holds one pixel value for each electrode. The video filter processor takes into account the latest spatial mapping information for each electrode.

The filtering algorithm will now be discussed. In particular a Difference of Gaussian DoG filter is used as the video filter processor .

According to an embodiment of the present disclosure the DoG filter can be determined by 4 parameters 

The filter kernel can be defined as sigmaCenter 1 sigmaCenter sqrt 2 pi exp 22 sigmaCenter 2 sigmaSurround 1 sigmaSurround sqrt 2 pi exp 22 sigmaSurround 2 

A digitized version of the kernel can be obtained by sampling on the continuous kernel. A set of parameters are chosen to help enhancing edge information in the video frame while preserving the relative brightness levels of the individual pixels. By way of example the parameters that can be used are 

The two dimensional convolution of the input rawVideoFrame with the DoG kernel is expensive to compute especially on the DSP chip of the VPU of . One can observe that although the DoG kernel is not separable the underlying gaussian kernels are. sigmaCenter centerGaussianKernel sigmaSurround surroundGaussianKernel 

In view of the separability of the Gaussian kernels the filtering can be done with a filter by row then by column scheme. In addition this can help take advantage of the hardware acceleration in DSPLIB for one dimension convolution.

The result of the DoG filter is an image of the same size as the rawVideoFrame 20 12 . The final step of the filter processor is to sample at the locations required in the spatial map. The output will be 60 brightness values one for each electrode.

In this mode the video decoder is configured to capture a raw pixilated image from the NTSC source based on the current zoom setting. Video data for stimulation that has been indicated as invalid should not be used. This will occur when the camera is disconnected or if communications problem occur with the video decoder .

An image processing filter will be used to process the raw pixel image. The final filtered image should always be a 6 10 grayscale pixilated image. To compensate for possible non linear spatial mapping of electrode response to electrical stimulation an arbitrary pixel to electrode array space mapping can be used to map each of the 60 electrodes to a particular image pixel. This mapping can be modified by the user.

Further brightness mapping to map for each electrode the pixel intensity of the electrode to current amplitude can be used. This mapping can be modified by the user.

The output mapping can be alterable. Each of the individual pixels can have a locus set and saved in the PC program. This locus shall be mapped to the video image pixel. The video image shall determine a pixel luminance value for this pixel.

The mapping of luminance to pixel electrical stimulation parameters shall allow the PC program to set a mapping of luminance to pixel electrical stimulation parameters through providing a mapping constant linear or exponential of the following variables to electrical stimulation parameters through a range settable for each pixel and based on how many electrodes are presently on.

The following electrode driver variables shall not be controlled by luminance but set to values by the PC program

The user shall have the option of programming a shorting command during times in which the electrode is not stimulating.

According to a further embodiment of the disclosure the system can contain the following luminance vs. electrode stimulation mapping choices 

The pixel location can relate to a 4 by 4 output map 16 pixels and can be limited for x and y values between and including 0 and 15. The PC settable value of BinaryFilterPoint can be used as a floor for camera illumination. The PC settable value of BinaryRange which is 0xFF BinaryFilterPoint can be used as the range for the camera range.

2 Linear a linear transformation between pixel brightness and amplitude is used according to the formula as computed in A not clinical units CU Amplitude pixelValue BinaryFilterPoint BinaryFilterRange Amplitude Range minimum amplitude. 3 Exponential an exponential transformation between the pixel brightness and amplitude is used according to the formula as computed in clinical units CU not A Amplitude pixelValue BinaryFilterPoint BinaryFilterRange Amplitude Range minimum amplitude.

2 Linear a linear transformation between pixel brightness and pulse width is used according to the formula the pulse width range and amplitudes are in ms . PulseWidth pixelValue BinaryFilterPoint BinaryFilterRange puslewidthRange minimum pulsewidth. 3 Exponential an exponential transformation is used in accordance with a factor of 5000 . This value was chosen as it is the value used in the Clarion output range setting. In the following formula the pulse widths are first converted into clinical units CUs using a logarithmic base 5000 function and then the range and amplitudes computed in CUs. PulseWidth pixelValue BinaryFilterPoint BinaryFilterRange puslewidthRange minimum pulsewidth.

A current filter can be used to reduce the amount of current that is sent to the patient based on the electrodes that are turned on. Each electrode is compared to a PC settable ON value of each electrode and a COUNT is made of the number of ON electrodes. Each electrode s clinical units is reduced by a clinical units that is dependent upon COUNT if the remaining current on the electrode is greater than a minimum current settable for each individual electrode.

A maximum number of patient setting e.g. 7 can be established. For each of the 16 electrodes the applicable parameters as set by any individual patient setting can be 

Each patient setting can have a unique BinaryFilterPoint and corresponding BinaryFilterRange. Each patient setting can have a filter implementation. The system can startup with the current Patient Setting pointing to the first Patient Setting on the list. The PC e.g. laptop of should not be able to disable the first Patient Setting on the list. The PC can have the ability to download electrode stimulation parameters to any valid Patient Setting on the VPU.

The PC can have the ability to upload any valid Patient Setting on the VPU for inspection. The PC can have the ability to disable any valid Patient Setting except the first one on the VPU. Any valid Patient Setting gets automatically enabled when the PC sets it.

The user can have the ability to scroll through the enabled Patient Settings in a circular fashion. An audible feedback is provided to the user designating which particular Patient Setting s he is on. The forward telemetry can complete the ongoing stimulation first with the parameters of the previous Patient Setting. The pulse waveform parameters can then be updated with the parameters from the next scrolled Patient Setting.

The PC can have the ability to set the current Patient Setting to any valid enabled Patient Setting on the list. The PC can have the ability to upload the current Patient Setting on the VPU at any time.

Accordingly what has been shown are methods and systems for providing stimulation inputs to a visual prosthesis implant. While these methods and systems have been described by means of specific embodiments and applications thereof it is understood that numerous modifications and variations could be made thereto by those skilled in the art without departing from the spirit and scope of the disclosure. It is therefore to be understood that within the scope of the claims the disclosure may be practiced otherwise than as specifically described herein.

