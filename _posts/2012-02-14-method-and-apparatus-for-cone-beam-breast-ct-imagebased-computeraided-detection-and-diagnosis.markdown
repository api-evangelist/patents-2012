---

title: Method and apparatus for cone beam breast CT image-based computer-aided detection and diagnosis
abstract: Cone Beam Breast CT (CBBCT) is a three-dimensional breast imaging modality with high soft tissue contrast, high spatial resolution and no tissue overlap. CBBCT-based computer aided diagnosis (CBBCT-CAD) technology is a clinically useful tool for breast cancer detection and diagnosis that will help radiologists to make more efficient and accurate decisions. The CBBCT-CAD is able to: 1) use 3D algorithms for image artifact correction, mass and calcification detection and characterization, duct imaging and segmentation, vessel imaging and segmentation, and breast density measurement, 2) present composite information of the breast including mass and calcifications, duct structure, vascular structure and breast density to the radiologists to aid them in determining the probability of malignancy of a breast lesion.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09392986&OS=09392986&RS=09392986
owner: Koning Corporation
number: 09392986
owner_city: West Henrietta
owner_country: US
publication_date: 20120214
---
The present application is a national stage of PCT US2012 025141 filed Feb. 14 2012 which claims the benefit of U.S. Provisional Patent Application No. 61 442 559 filed Feb. 14 2011 the entire disclosures of which are hereby incorporated by reference in their entirety into the present disclosure.

This invention was made with government support under Grant Nos. R01 9 HL078181 and 4 R33 CA94300 awarded by National Institutes of Health. The government has certain rights in the invention.

The present invention is directed to breast imaging and more particularly to the provision of three dimensional 3D breast information including 3D location and measurement of mass and calcifications 3D duct structure 3D vascular structure and volumetric breast density.

Many researchers have made significant progress in breast lesion auto detection on mammograms and Breast MRI BMRI . Computer aided auto detection technology in those two imaging modalities has achieved good results. However mammography and MRI have their inherent limitations. Due to breast tissue overlap even large tumors and some calcification clusters are obscured in mammograms.

Although it is reported that CAD computer aided detection and diagnosis on mammography increases sensitivity it is also reported that there is no significant improvement with the CAD applied to the mammograms. The effectiveness of the CAD application to mammography seems unclear.

BMRI cannot detect calcifications which are important signs for early breast cancer and DCIS and are evident in up to 50 of breast cancers not associated with a mass. Although it is a three dimensional 3D visualization of the breast BMRI has limited spatial resolution in plane resolution of 1 mm and slice thickness of 2 3 mm . Small lesions may be missed or incorrectly characterized due to the resolution limitation.

Although BMRI based CAD has had some success in distinguishing benign from malignant masses acknowledged limitations of the system include an inability to consider T2 weighted images. Thus the system potentially may miss useful additional morphology information available in those sequences. In addition current BMRI based CAD cannot improve radiologist accuracy in distinguishing malignant from benign MRI screen detected lesions because of its poor DCIS detection sensitivity.

Another breast imaging modality is digital breast tomosynthesis DBT which has a sensitivity of up to 85 . However DBT collects projections over limited angles resulting in spatial resolution loss in the direction perpendicular to the detector. Although CAD in DBT can help radiologists to handle a large amount of data the resolution loss limits its ability to detect subtle breast lesions and calcification clusters so that it is likely that DBT must be used with digital mammography for breast cancer screening and diagnosis.

Ultrasound based CAD US CAD has also been explored. Though ultrasound has considerable potential it also has well known limitations. The technique is difficult to teach and perform. Also differentiating between benign and malignant lesions can be challenging. The addition of ultrasound could also lead to unnecessary biopsies of benign lesions. Another major limitation of US CAD is the fact that microcalcifications are difficult to image with ultrasound. In addition US CAD is limited by the relatively poor spatial resolution of ultrasound. In summary different breast imaging modalities have different characteristics that require the development of the modality based CAD to further improve radiologists accuracy and efficiency.

Radiographic breast parenchymal pattern also referred to as breast density is an important factor associated with the development of breast cancer. Currently most breast density research is based on mammography technology. Most breast density description uses the BI RADS breast density terminology. In BI RADS four categories of breast density are defined 

However breast tissue overlaps in two dimensional mammography projection images. The breast density measurement may be inaccurate using mammograms.

In summary different breast imaging modalities have different characteristics that require the development of the modality based CAD to further improve radiologists accuracy and efficiency.

There is thus a need in the art for a CAD system working with CBBCT images to provide 3D composite breast information.

There is also a need in the art to improve accuracy and efficiency in radiologists diagnostic performance.

It is therefore a primary object of the invention to provide 3D composite breast information which includes breast density evaluation mass and calcification detection and measurement breast vascular structure segmentation and breast duct segmentation.

It is another object of the invention to provide method to accurately evaluate breast density with CBBCT images.

It is yet another object of the invention to provide three dimensional location information of breast masses with CBBCT images.

It is yet another object of the invention to provide three dimensional characteristics of breast masses with CBBCT images.

It is yet another object of the invention to provide three dimensional location information of breast calcifications with CBBCT images.

It is yet another object of the invention to provide three dimensional characteristics of breast calcifications with CBBCT images.

It is yet another object of the invention to provide three dimensional characteristics of breast vascular system with CBBCT images.

It is yet another object of the invention to provide three dimensional characteristics of breast ducts with CBBCT images.

To achieve the above and other objects the present invention is directed to a CAD technique based on cone beam breast computed tomography CBBCT . Cone Beam Breast CT is a three dimensional breast imaging modality with soft tissue contrast superior to that of mammography high contrast resolution and no tissue overlap. With those advantages it is possible to measure volumetric breast density accurately and quantitatively with CBBCT 3D images. Cone Beam Breast CT is a novel breast imaging technology using cone beam CT technology and an ergonomically designed imaging system. CBBCT delivers true three dimensional breast images without tissue overlap. The resolution of CBBCT images is 3D isotropic with the voxel size as small as 155 m. Even without intravenous contrast injection the CBBCT soft tissue contrast to noise ratio is as high as 8. The breast coverage of CBBCT is comparable to and even larger than that of mammography. With those novel features CBBCT images of the breast can be an ideal tool to quantitatively measure volumetric density of the breast.

CBBCT based computer aided diagnosis CBBCT CAD technology is a clinically useful tool for breast cancer detection and diagnosis that will help radiologists to make more efficient and accurate decisions. The CBBCT CAD is able to 1 use 3D algorithms for image artifact correction mass and calcification detection and characterization duct imaging and segmentation vessel imaging and segmentation and breast density measurement 2 present composite information of the breast including mass and calcifications location and characteristics duct structure vascular structure and breast density to the radiologists to aid them in determining the probability of malignancy of a breast lesion.

The novelties of the CBBCT CAD system include 1 The first 3D CAD system based on CBBCT technology 2 The first CAD system to provide composite breast information that is not available from other modalities based CAD systems 3 Prominent accuracy and efficiency improvements in radiologists diagnostic performance.

James C. Bezdek Pattern Recognition with Fuzzy Objective Function Algorithms Kluwer Academic Publishers Norwell Mass. 1981

Xiaohua Zhang Ruola Ning and Dong Yang Three dimensional breast masses auto detection in cone beam breast CT Proc. SPIE 2009 7260 726027.

Xiaohua Zhang Ruola Ning and Jiangkun Liu Computer aided breast calcification auto detection in cone beam breast CT Proc. SPIE 2010 7624 76242M.

D Chen R Fahmi A A Farag R L Falk G W Dryden Accurate and fast 3D colon segmentation in CT colonography Proc. of ISBI 2009 490 493.

Dong Yang Ruola Ning Yong Yu David Conover and Xianghua Lu Implementation and evaluation of the half scan scheme based on CBCT cone beam CT system Proc. SPIE 5368 542 2004 .

1. U.S. Pat. No. 8 023 767 Method and apparatus for 3D metal and high density artifact correction for cone beam and fan beam CT imaging

2. U.S. Pat. No. 7 949 095 Methods and apparatus for differential phase contrast fan beam CT cone beam CT and hybrid cone beam CT

5. U.S. Pat. No. 7 362 845 Method and apparatus of global de noising for cone beam and fan beam CT imaging

6. U.S. Pat. No. 6 987 831 Apparatus and method for cone beam volume computed tomography breast imaging

7. U.S. Pat. No. 6 618 466 Apparatus and method for x ray scatter reduction and correction for fan beam CT and cone beam volume CT

8. U.S. Pat. No. 6 504 892 System and method for cone beam volume computed tomography using circle plus multiple arc orbit

9. U.S. Pat. No. 6 480 565 Apparatus and method for cone beam volume computed tomography breast imaging

10. U.S. Pat. No. 6 477 221 System and method for fast parallel cone beam reconstruction using one or more microprocessors

12. U.S. Pat. No. 6 075 836 Method of and system for intravenous volume tomographic digital angiography imaging

A preferred embodiment will be set forth in detail with reference to the drawings in which like reference numerals refer to like elements or steps throughout.

The first step is skin removal. Although the skin in CBBCT images has higher intensity than the fatty stroma its intensity is only slightly higher than that of the glandular tissue. A simple thresholding cannot segment the skin from other tissue. Based on the fact that the skin is on the outermost layer of the whole breast a morphological process is proposed to remove the skin from the breast in CBBCT images.

1. A histogram thresholding method is applied to the whole CBBCT image volume to separate the image into three distinct parts which have significant different intensities air fat and tissues including skin and glands .

2. Based on the fact that the skin is between the inner breast and the air a morphological 3D erosion operation is applied to erode the tissue between air and fat.

4. In case the glandular tissue is connected to the skin in CBBCT images during the erosion a global ratio of fat area vs. total edge area is recorded along the edge of the breast. When the ratio reaches 80 or another suitably chosen value the skin removal process stops.

Glandular tissue segmentation will now be explained. The fuzzy c means FCM algorithm is widely used for image segmentation. It is also used for breast density assessment in both mammography and breast MRI. In CBBCT images due to the high soft tissue contrast FCM is also an effective algorithm to segment glandular tissue from fat. The FCM is taught in James C. Bezdek Pattern Recognition with Fuzzy Objective Function Algorithms Kluwer Academic Publishers Norwell Mass. 1981.

where xis the data vector to be clustered cis the center vector of the jth cluster uis the degree of the vector xin the jth cluster m is the fuzziness exponent N is the number of total data vectors and C is the number of total clusters. is a distance function measuring the similarity between any data vector and cluster center.

The fuzzy c means clustering algorithm iteratively optimizes the objective function Jby updating uand cwith

Bias areas include low density glandular tissue with attenuation as measured in Hounsfeld units or HU close to the fat and non uniform areas caused by imaging artifacts. To achieve better accuracy of tissue segmentation the bias areas need to be handled. In addition to the clusters for air fat and glands an extra cluster is used for bias areas.

1. A local contrast process is applied to the CBBCT images after skin removal. The local contrast is based on the following equation 

Here f x y z is the HU of a voxel at a position x y z and R is a local cube with size N N N. By this process the non uniform artifact is reduced.

2. Voxels in the bias area are extracted to go through a second clustering using the images from step 1. The cluster number here is set to 3. The cluster with the highest center value is considered to be glands and the rest of clusters are considered to be fat.

3. Combine the clustering results from first clustering and second clustering to yield a final result of air fat and gland segmentation.

After the CBBCT images are segmented into skin fat and glands the percentage of each tissue with respect to the whole breast volume can be calculated.

From the CBBCT clinical database 5 patient data sets were selected for a preliminary experiment. Each patient data set had its mammography records reviewed by a radiologist and its breast density category was assigned based on the mammograms. The computer aided breast density evaluation was applied to the CBBCT images of each patient. shows the mammograms and the CBBCT slices of 4 cases used in this study corresponding to the 4 BI RADS breast density categories. More specifically that figure shows four clinical cases with MLO mammogram images and CBBCT slice images. Top row mammography images Bottom row corresponding CBBCT slices. Left column BIRADS 1 fatty breast Middle left column BIRADS 2 scattered breast Middle right column BIRADS 3 Hetero dense breast Right column BIRADS 4 Extreme dense breast.

The CBBCT breast density auto evaluation process is applied to each of the clinical cases. shows the skin removal results and shows the auto segmentation results. More specifically shows a original CBBCT image b CBBCT image with skin removed and c skin image. shows a original CBBCT image with skin removed b fat tissue area and c glandular tissue area.

Based on the segmented image the percentages of skin fat and glands could be acquired. Table I lists the density measurement and compares it with the BI RADS category of each case.

Breast density changes over time. An increase in breast density is associated with greater risk of breast cancer regardless of the original breast density measurement. Accurate measurement over time is important for active surveillance of the breast density change. The breast density auto evaluation provides accurate volumetric measurement to detect the changes of density hence timely cancer risk assessment can be possible.

Table I above gives the comparison result between CBBCT breast density measurement and the mammography based BI RADS category. As can be seen from the table there are obvious disagreements between those two systems especially within breasts with higher density categories in BI RADS. Measuring breast density with two dimensional mammograms and true three dimensional CBBCT images can yield different results for the same breast. A new breast density measurement system may be defined based on CBBCT images.

The preferred embodiment is not limited to measuring breast density. Mass detection and calcification detection will now be disclosed. The algorithm is taught in Xiaohua Zhang Ruola Ning and Dong Yang Three dimensional breast masses auto detection in cone beam breast CT Proc. SPIE 2009 7260 726027.

Abnormal density and structural distortion are radiographic signs for radiologists to detect masses. In 3D CBBCT images breast masses are observed as congregated volumetric regions which have a denser structure than the surrounding normal tissues. Malignant masses have irregular or spiculated margins while benign masses usually have smooth margins. The high contrast of CBBCT images reveals the density difference between tissues. A 3D mass detection algorithm takes advantage of high contrast resolution and the 3D characteristic of the CBBCT images.

In CBBCT high contrast resolution reveals the contrast changes of tissue components across voxels. The 3D detection algorithm is able to measure these changes and uses the difference between masses and normal tissues for suspicious region detection. According to the preliminary study on 14 pathology proven masses after image calibration the average contrast between masses and their surrounding tissues ranged from 10 to 80 HU. Other characteristics such as the gradient congregation of the mass were also used to distinguish mass from normal tissue. In the preliminary studies a 3D weighted average algorithm was applied followed by a 3D iris filtering to CBBCT volume images to highlight the congregate tissue volume. The highlighted areas are selected as candidates of breast masses. In the preliminary result 12 of the 14 masses were correctly detected. After the mass regions are detected the corresponding measurements of each region are calculated. The measurements include density size volume and shape descriptors. The marked results and corresponding measurements will be provided as output results.

Calcification detection will now be disclosed. The algorithm is taught in Xiaohua Zhang Ruola Ning and Jiangkun Liu Computer aided breast calcification auto detection in cone beam breast CT Proc. SPIE 2010 7624 76242M. In CBBCT images calcifications have high contrast to the surrounding tissues and high HU variations both inside the calcification area and at the edges. The contrast between calcification and background material is from 200 HU to 800 HU and the HU standard deviation can be more than 200 HU. A calcification auto detection scheme has been developed to locate the calcifications within CBBCT images. A 3D local thresholding process and a histogram thresholding process are first applied to the CBBCT images to select all voxels with relatively high HU value and HU variation with respect to the neighborhood voxels. To further reduce false positives six features are extracted from each remaining connected voxel object. The features are fed into an artificial neural network ANN which is trained with known calcification features. The ANN output values are used as criteria to differentiate calcification objects from false positive objects. A preliminary study achieves sensitivity of 95 with average 10 false positives calcifications per case. illustrates one example of CBBCT calcification auto detection in which image a indicates known calcifications and image b indicates eth results of the calcification algorithm. After the detection measurements of the calcifications will be provided including cluster size number of calcifications in clusters and shape descriptors.

Breast ducts and blood vessels can be segmented. Segmenting algorithms are known in the art e.g. for segmenting colons. A suitable algorithm is taught in D Chen R Fahmi A A Farag R L Falk G W Dryden Accurate and fast 3D colon segmentation in CT colonography Proc. of ISBI 2009 490 493. Such segmentation can be used for active surveillance of duct carcinoma in situ DICS and abnormal vasculature relating to tumors.

Artifact correction will now be disclosed. A suitable method is taught in Ning R Apparatus and Method for X ray Scatter Reduction and Correction for Fan Beam and Cone Beam Volume CT. U.S. Pat. No. 6 618 466 issued on Sep. 9 2003 and PCT US03 04871.

Scattering is one of the major problems that are associated with CBBCT because the large area flat panel detector in a CBBCT system receives scattered x rays as well as primary x rays. At 49 kVp the scatter to primary ratio can be as high as 0.5 for an average sized breast. Scattering produces inaccurate CT numbers reduces tissue contrast and causes cupping artifact in the reconstructed CBBCT images. Given the roughly symmetric geometry of a breast and the slowly varying nature of scattered radiation the scattered radiation is estimated based on the breast shape in a projection image and the projection image is corrected by subtracting the scattered radiation. As the shape and position and breast shadow are different across different projection images such a correction is performed for all projections. The axial and longitude uniformity can be improved to 20 HU and 40 HU respectively.

Motion artifacts are associated with patient movement and breathing during the scan appearing as blurs in the reconstruction images. Usually the moment of motion can be identified by examining projection images. The data before or after this moment can be considered as motion free data which can be used for reconstruction with half scan algorithms. A suitable algorithm is taught in Dong Yang Ruola Ning Yong Yu David Conover and Xianghua Lu Implementation and evaluation of the half scan scheme based on CBCT cone beam CT system Proc. SPIE 5368 542 2004 . This method can efficiently remove motion artifacts.

A system on which the preferred or another embodiment can be implemented is set forth in U.S. Pat. No. 6 480 565 whose disclosure is hereby incorporated by reference in its entirety into the present disclosure. of that patent which is reproduced herein as shows an exemplary device. In the scanner the patient P rests on an ergonomically formed table so that the breast B to be scanned descends through a hole in the table into a safety cover .

Below the table a gantry supports a detector and an x ray tube one on either side of the safety cover . The gantry is turned by a motor to be rotatable around an axis A passing through the safety cover so that as the x ray tube travels along an orbit O the breast B remains in the path of a cone beam C emitted by the x ray tube . The gantry is also movable by a motor to go up and down along a vertical path V. Alternatively the table can be moved up and down along a vertical path V. The detector can be moved toward and away from the axis A by a motor to change the magnification factor if necessary.

In some embodiments a piston may be used to push the nipple toward the chest wall to reduce z direction coverage by a couple of centimeters although usually the breast does not have to be re shaped.

A contrast injector can be provided for contrast enhanced tomographic imaging angiogenesis studies and some other dynamic contrast studies. Various contrast injection media such as iodine are known in the art. It is not always necessary to inject a contrast medium into the patient.

Image Artifact Correction Modules The image artifact correction modules are executed either before or after the CBBCT reconstruction. As shown the modules include pre correction and post correction . The pre correction is performed on the projections acquired from the CBBCT scan. A suitable method is taught in Ning R Apparatus and Method for X ray Scatter Reduction and Correction for Fan Beam and Cone Beam Volume CT. U.S. Pat. No. 6 618 466 issued on Sep. 9 2003 and PCT US03 04871. The post correction is performed on the isotropic 3D images from the CBBCT reconstruction.

Detection and Segmentation Modules The four detection and segmentation modules are interconnected. Those modules are density assessment duct segment detection calcification detection and mass detection . The density assessment algorithm has been described above. A suitable calcification detection algorithm is taught in Xiaohua Zhang Ruola Ning and Jiangkun Liu Computer aided breast calcification auto detection in cone beam breast CT Proc. SPIE 2010 7624 76242M. A suitable mass detection algorithm is taught in Xiaohua Zhang Ruola Ning and Dong Yang Three dimensional breast masses auto detection in cone beam breast CT Proc. SPIE 2009 7260 726027. The users are able to choose one or multiple modules for better diagnostic assistance. Each of the modules is designed to run on both the CPU and the GPU to reduce the processing time. The output results of each module can be superimposed so that radiologists can combine different information to make an accurate decision.

The Task Manager is the main interface of the CAD system between the users and the CAD modules. System connections data send receive configurations and task scheduling queuing are defined through the task manager. The task manager organizes all applicable cases and dispatches the tasks to the detection and segmentation modules based on the specific requirements for each case. The task manager also plans all possible resources in the system and assigns the resource to the appropriate modules.

Data Access Interface This is a DICOM interface to PACS Image Archive system for image data retrieve store and the radiologists feedback annotation or report for further processing. Multiple DICOM outputs including DICOM printers Structured Reporting DICOM 6000 Overlay Secondary Image Capture and RTSS are supported.

CAD Server The CAD Server provides the interface for all clients and external PACS or image archive systems as well as DICOM printers . It is equipped with highly configured parts to provide fast and reliable services. The CAD server accepts the schedules from pre configured tasks or the user inputs read data from the PACS Archive system dispatches the computation tasks to the CAD workstations receives the result from the workstations and writes the CAD reports back to the PACS Archive system or prints the reports.

CAD Workstation The major functional modules of the CAD system are running on the high performance workstation. It provides fast and reliable computation to satisfy the practical requirements. The workstation is attached to the server by hi speed connection. Multiple workstations can be installed and connected in each system to perform the tasks parallelly to provide enough computation capability.

Thin Client The thin client gives users easy access to the system. It can be browser based application or stand alone GUI application. It communicates with the CAD server within the intranet or over the internet to provide the services from anywhere with internet connection. The users setup the configurations and schedule tasks on the CAD server through the intuitive GUI provided by the thin client.

With the parallel processing capability of the hardware and software design the total processing time of the CBBCT CAD system is expected to be within 5 minutes.

While a preferred embodiment has been set forth in detail above those skilled in the art who have reviewed the present disclosure will readily appreciate that other embodiments can be realized within the scope of the invention. For example recitations of specific hardware and of numerical values are illustrative rather than limiting. In addition the disclosed cone beam CT image based CAD method and system can be used for other cone beam CT imaging applications such as angiography imaging and lung imaging. Therefore the present invention should be construed as limited only by the appended claims.

