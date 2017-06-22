---

title: Software internationalization estimation model
abstract: Various technologies related to estimating programming effort to internationalize a software program are described. A sampling technique can be applied to the numerous program files that make up the software program. Stratification by impact point type can be supported. Historical data can be used to provide an accurate and reliable estimate without having to completely analyze all files in the software program
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09213543&OS=09213543&RS=09213543
owner: Infosys Limited
number: 09213543
owner_city: Bangalore
owner_country: IN
publication_date: 20120222
---
Due to growing globalization in the software development field there is an increasing demand to internationalize software programs. However accurately determining the amount of programming effort needed to complete internationalization sometimes called i18n of a software program can be difficult and time consuming.

For example an analyst can estimate the amount of effort needed by reviewing the entire software program code for various conditions related to internationalization. However typical software applications can involve a huge volume of files and myriad lines of code making such estimation a major undertaking in itself.

Although various approaches have been taken to address such difficulties there is still a need to address the complexities of estimating the amount of programming effort needed to complete internationalization in an efficient and accurate manner.

A variety of techniques can be used for estimating the amount of programming effort needed to complete internationalization of a software program. A tool can estimate the amount of effort needed and assist in the estimation process.

As described herein a variety of other features and advantages can be incorporated into the technologies as desired.

The foregoing and other features and advantages will become more apparent from the following detailed description of disclosed embodiments which proceeds with reference to the accompanying drawings.

The technologies described herein can be used for a variety of internationalization estimation scenarios. Adoption of the technologies can provide an efficient technique for estimating the amount of programming effort needed to complete internationalization of a software program.

The technologies can be helpful to those wishing to estimate an amount of programming effort for a programming project involving internationalization of a software program. Beneficiaries include information technology solution providers who wish to provide accurate estimates for proposals to clients whether internal or external. Such clients can also greatly benefit from the technologies because they enjoy accurate and credible proposals targeted to their specific application.

The tool can be included as part of another internationalization analysis tool or be used in conjunction with such a tool e.g. to analyze software programs from an internationalization perspective .

In practice the systems shown herein such as system can be more complicated with additional functionality more complex inputs and the like.

As described herein the tool can handle a plurality of internationalization impact point types and the sample tool can be utilized accordingly.

In any of the examples herein the inputs outputs and tools can be stored in one or more computer readable storage media or computer readable storage devices.

At details of a software program are received. Such details can include the number of files the content of the files which files have internationalization impact points and the like as described herein.

At the program details are analyzed to estimate the programming effort to internationalize the program. As described herein a sampling technique can be employed.

Such a sampling technique can comprise calculating a sample size using a confidence interval and a confidence level and the like.

The method and any of the methods described herein can be performed by computer executable instructions stored in one or more computer readable media e.g. storage or other tangible media or stored in one or more computer readable storage devices.

In any of the examples herein programming effort can be estimated in any of a variety of metrics. For example function points lines of code hours e.g. worker hours and the like can be used.

In practice the programming effort can then be converted into a monetary e.g. dollar euro or the like measure and included as part of a proposal that involves internationalizing the software program.

Because the estimated programming effort is an estimate it can be provided as a range e.g. within two values according to a confidence interval. The range can be used as desired. For example a conservative practice may be to use the higher end of the range to avoid underestimating the amount of programming effort.

Inputs to the sampling tool can include the software program files of a software program that is to be internationalized e.g. for which an estimate of the amount of programming effort required to internationalize is desired . The program files can be the overall program files a sampling frame or strata e.g. stratified by impact point type as described herein.

In the example the sampling tool can output a subset of the program files A K. In practice a reference or count of program files can be indicated rather than outputting the text of the program files A K. A program file K can have one or more candidate internationalization impact points A N.

As part of the sampling process the sampling tool can be configured to receive a count of the overall program files having candidate internationalization impact points and calculate based on a confidence interval and a confidence level a sample size indicating size of a subset of the overall program files to be taken from the program files.

An analysis tool can be used to determine e.g. for respective of the subset of program files which of the candidate internationalization impact points A N are true internationalization impact points .

An extrapolation tool can take information including that from the sampling process as input and output an estimated amount of programming effort to internationalize the software program. The extrapolation tool can be configured to receive a number of candidate impact points for the subset of the program files a number of true impact points for the subset and a number of candidate impact points for the overall program files having candidate internationalization impact points and calculate based on historical programming efficiency data an estimated number of hours to complete internationalization of the software program.

As described herein a variety of features can facilitate accurate and efficient determination of an internationalization estimate.

At for a software program comprising an overall plurality of program files a sampling technique is applied to the program files selecting a subset e.g. sample of the program files out of the overall plurality of program files e.g. a sampling frame of files containing one or more candidate internationalization impact points . Such a sampling technique can involve determining the files involved and counting them e.g. to determine a number of the program files . As part of the process the files themselves may be received.

At the subset of program files are analyzed identifying candidate internationalization impact points e.g. determining that a certain number of candidate internationalization impact points appear in the subset of program files . In practice an analysis tool can be used or manual analysis of code can be performed. A count of the number of candidate internationalization impact points can be generated e.g. per program file .

In practice candidate internationalization impact points can also be identified for the other files e.g. the program files other than those in the subset chosen by sampling such identification can be performed at the same time the subset is analyzed or at some other time.

At the true internationalization impact points out of candidate internationalization impact points in the subset of program files are identified. For example a number of the candidate internationalization impact points that are true internationalization impact points can be identified e.g. a count is determined . Various conditions as described herein can be detected to indicate that a candidate internationalization impact point need not be addressed as part of the internationalization process such an impact point is not a true internationalization impact point. The identification can be performed per file. Results can be stored separately per file or combined as described herein.

At the amount of programming effort to internationalize the software program is extrapolated. Such extrapolation can be based on the number of candidate internationalization impact points and the number of true internationalization impact points. The extrapolation indicates an estimate of the overall effort needed to internationalize the software program for the overall files. In practice extrapolation can extrapolate an estimated number of true internationalization impact points for the overall plurality of program files. As noted herein extrapolation can calculate an estimated amount of worker hours to internationalize the program e.g. based on estimated number of true internationalization impact points and historical data indicating programmer productivity . As described herein certain files e.g. not having candidate internationalization impact points can be excluded from processing.

As described herein a sampling technique can specify a confidence interval and confidence level. In such a case the amount of programming effort can take the form of an estimate and can be given as a range or a particular number in a variety of units e.g. function points time units or the like .

In any of the examples herein a software program can be any of a variety of software programs or applications whether web based desktop cloud enabled or the like. The technologies described herein can support software programs in a variety of programming languages the details of which are independent of the principles of operation.

As described herein such programs can comprise a plurality of program files. Such files can include executable code whether in the form of source code scripts or the like.

In any of the examples herein a variety of sampling techniques can be applied resulting in a selected subset of program files. Sampling techniques can include calculating a sample size using a z score corresponding to a confidence level.

Having determined a sample size a variety of sampling techniques can be used to select the sample from the source population. For example systematic sampling can be used. In such a technique the population can be ordered e.g. by number of occurrences of candidate impact points and a subset of the program files can be selected by choosing files at regular intervals e.g. starting at some random file every subsequent nth file is selected in the sample where n population size sample size . In practice the starting element is not the first in the list but chosen randomly between the first and nth element.

Stratification can be applied as described herein leading to different sample sizes and thus different samples for different internationalization impact point types.

In practice a separate tool for calculating sample size can be provided for use by those engaged in effort estimation. Taking inputs as described herein the sample size calculator can generate a recommended sample size that will support a given confidence interval and confidence level.

In any of the examples herein internationalization impact points can be any of a variety of conditions detected in software program files that require remediation to internationalize the program.

For example for a software program that has not been internationalized a hard coded text string may be of a particular human language e.g. French English or the like . If the string is displayed to a user internationalization requires that the string be externalized so that any of a variety of strings in any of a variety of human languages can be used depending on what language is selected for the program e.g. during installation in preferences selected by a user etc. . Thus remediation may require substituting different program code that refers to an external string rather than the hard coded string or some other technique.

Other types of internationalization impact points include occurrences of non Unicode application program interfaces e.g. including invocations thereof occurrences of non Unicode data types e.g. including usages thereof .

Still other types of internationalization impact points include date time fields number formatting and the like.

In any of the examples herein candidate internationalization impact points can be conditions detected in software program files that are suspected to be e.g. tend to indicate internationalization impact points.

A true internationalization impact point is one that indeed needs to be addressed during internationalization. An example is a hard coded string that needs to be externalized e.g. stored outside the program file or outside the source code to achieve internationalization.

The effort to verify that a candidate internationalization impact point is a true impact point is typically greater than simply identifying the candidate in the first place. For example in the case of hard coded strings some strings may not be visible to a user may only be used in debugging logs or the like. In such a case while the string could be externalized in practice it is typically not required per internationalization requirements. Accordingly including such impact points in an estimate overestimates the amount of work required. Such a candidate is sometimes called a false positive. 

In some software programs the number of false positive candidate internationalization impact points can number in the thousands which would lead to great overestimation of the amount of effort to internationalize the software program.

In any of the examples herein candidate internationalization impact points can be identified as true internationalization impact points. Such identification can be accomplished via a tool. Or the determination can be done manually with the identification supplied for use by a tool.

For example in the case of hard coded strings or other impact point types a tool can scan source code to determine that the hard coded string or other item is never displayed to e.g. not visible to a user of the software program or is otherwise not relevant from an internationalization perspective. One such situation involves output to a debug log file e.g. debug log messages in which case the candidate internationalization impact point can be designated as not being true.

In practice techniques can designate candidate impact points as true or not true depending on detected conditions e.g. display to a user write to a log internal program use etc. . Those remaining can be considered true not true or unknown depending on configuration of the tool.

In any of the examples herein a number of files can be indicated by a count of the files. For example 1534 can indicate that there are 1534 program files having a particular condition e.g. they are candidate internationalization impact points true impact points or the like .

In any of the examples herein labor rates can indicate an amount paid for a unit of labor e.g. hourly labor rate monthly labor rate or the like .

In any of the examples described herein stratification can be used to separately apply the described sampling techniques and extrapolation for different internationalization impact point types e.g. different strata are used in place of the overall program files and or subsets thereof . The results can be summed together to arrive at a total amount of effort required to internationalize the program.

In any of the examples herein it may be detected that some program files may have no candidate internationalization impact points. In such a case processing for the files can be omitted e.g. from estimation calculations after such a determination is made. If stratification is supported processing for files having no candidate impact points for a particular impact point type can be omitted e.g. from estimation calculations for the particular impact point type after such a determination is made.

In this way a differentiation between a population e.g. the total number of files present in the program code and a sampling frame can be achieved. The sampling frame can be those program files having one or more candidate internationalization impact points. The sampling frame can be used as input for any of the sampling processes described herein.

For example when determining percentages applying percentages or the like processing for programming files having no internationalization impact points can ignore the files.

The tool can provide a rich set of features for sampling the program files . For example a user can specify a sampling technique whether to stratify as described herein and the like.

At information about a program file population is received. For example the number e.g. a count of program files having at least one candidate internationalization impact point can be received e.g. after being counted .

At an appropriate sample size for the program file population is determined. Such a determination can be based on the number of program files containing at least one candidate internationalization impact point. As described herein a confidence interval and a confidence level can be used during the determination.

At files e.g. a subset of the program files from the file population e.g. having at least one candidate internationalization impact point are selected via a sampling technique according to sample size. Any number of sampling techniques can be used including systematic sampling as described herein.

At the overall population of program files of a software program are analyzed to identify occurrences of various types of internationalization impact points. For example for the different internationalization impact point types a respective number of program files having candidate internationalization impact points of the internationalization impact point type can be counted.

At the program files are placed into groups e.g. strata according to the internationalization impact point type e.g. detected in the program files . The groups may overlap e.g. a program file can belong to more than one group . The respective number of program files having candidate internationalization impact points of the impact point types can be counted.

At sampling is performed separately on the separate program file groups. For example as described herein different sample sizes can be calculated for the different internationalization impact point types e.g. strata .

The number of candidate impact points in the overall set of program files can be for the program files of the software program for the program files other than those in the subset or for the program files having candidate impact points other than those in the subset.

In practice the tool can operate in stages. For example the output can be a number other than hours which is converted into hours e.g. via the historical data and the other factors .

At a count of candidate internationalization impact points and a count of true internationalization impact points are received. The count of candidate internationalization impact points can be divided into those for the subset e.g. sample of program files and those for the other files or those for the overall program files .

At historical data is received. Such historical data can include that from the organization that will be implementing the internationalization of the software program. For example such organizations typically keep or have access to historical data showing programmer productivity e.g. number of source lines of code SLOC produced per hour or the like .

At an estimated number of hours to internationalize the program can be calculated. Extrapolation can use the sampled program files to determine an observed rate of true impact points and extrapolate under the assumption that the observed rate will also be the rate for the other e.g. non sampled files. The estimated number of hours can be a range based on a confidence interval e.g. the confidence interval used during sample size calculation . As described herein stratification can be used for different internationalization impact point types.

In any of the examples herein extrapolation e.g. determining a percentage for the sampled files and applying it to the unsampled files can be used to calculate an estimate for the unsampled files. So at B the number of true internationalization impact points is shown as estimated e.g. in italics .

An observed percentage of true internationalization impact points for the subset of program files can be applied to a number of candidate internationalization impact points in other program files out of the overall plurality of program files.

An overall estimated number of true internationalization impact points can then be calculated as the sum of the observed true internationalization impact points and the extrapolated internationalization impact points.

At for sampled program files a number of observed true internationalization impact points and a number of candidate internationalization impact points is received. Such a number can also be received as a percentage or used to calculate a percentage.

At extrapolation is used to calculate an estimated number of true internationalization impact points for the unsampled program files e.g. by multiplying a percentage and the number of candidate internationalization impact points . Such extrapolation can be done on a file by file basis or for the files together.

At a sum of the observed true and estimated true internationalization impact points is taken resulting in an estimate of the overall effort to internationalize the software program.

In any of the examples herein an internationalization analysis tool can evaluate whether a candidate internationalization impact point is a true internationalization impact point and provide results of the evaluation. Evaluation can be done using a static approach e.g. without executing the code . Examples include detecting that a hard coded string is used in a debug log or the like as described herein.

The technologies described herein can be implemented in a Software Internationalization Estimation Model SIEM which is aimed at providing effort estimation for internationalizing an existing application product by taking into account the internationalization impact points at a very granular level e.g. the input data is collected by doing a static analysis of the code to get the number of hard coded strings non Unicode functions variables etc. . The quantitative data combined with other qualitative data such as internationalization support for installers build scripts etc. can be used to arrive at a reasonably accurate internationalization effort estimate.

SIEM can include an approach for carrying out the internationalization gap analysis in an existing application e.g. based in Java C C or the like . Analysis is done based on the level of Internationalization desired e.g. string externalization number formatting message formatting etc. . Some of the requirements also vary from region to region e.g. bi directional text support for mid eastern countries . Apart from such requirements the impact of which can be measured by static code analysis gap analysis can also take into account one or more of the following areas which impact the internationalization of applications 

Gap analysis can list down all areas within and outside the application which can impact the internationalization of the application.

Code analysis can be carried out during gap analysis. Code analysis can be done manually and also with the help of static code analysis tools. For large applications a combination of both automated code analysis and manual analysis may be used. The code analysis can 

For large applications with a huge code base it may not be possible to manually analyze each and every file. Tools to perform static code analysis can be used to provide a high level assessment of the code which can be followed by data sampling as described herein and manual analysis.

Code analysis using static analysis tools can give a raw output of the internationalization impact points in the code e.g. candidate impact points . It is quite possible that not all reported impact points need to be modified for internationalization since it is also important to analyze the scenario in which they are being used. In order to further refine the output of the static analysis tools a manual code analysis can be used. If the files to be manually analyzed are too many in number a sampling approach can be followed.

A list of 3party tools and APIs can be compiled and they can be analyzed for internationalization support. If the 3party tools do not provide internationalization support in the current version support can be check to see if it is available in later versions. Modifications to 3party tools and APIs can be checked to see if they come under the scope of the internationalization exercise.

The application build script can be analyzed to check if it can support builds for different locales. Changes to build scripts might be required in order to create executables or jars which support multiple locales.

If the application uses an installer to get installed it can be checked if the Installer software itself supports Unicode. The customer might have the following requirements related to installations 

If the application uses reporting tools like Crystal Reports Cognos Reports etc. they can be analyzed to check the following 

The internationalization estimation model can work on quantitative data obtained by static code analysis. For example the following data can be obtained by doing a static code analysis using a developed internationalization analysis tool 

Based on certain pre defined internationalization rules for a particular language the internationalization analysis tool can get the number of instances which match the criteria. Because some tools are not imbued with the intelligence to understand the correctness of context of use of detected instances all of such instances may not require to be changed for internationalization compatibility. A sampling approach can then be defined to filter the results to arrive at the number of instances that need actual changes. With these numbers an extrapolation can be done to estimate the percentage of detected instances which actually need changes. The numbers obtained here are then used in the estimation model to calculate the effort.

For example an internationalization analysis tool may detect a total of 50 000 hard coded strings in the application. Based on manual analysis of the code it is found that about 20 000 hard coded strings are part of the debug log messages which need not be internationalized externalized . That number should be deducted from the total detected by the tool. So we end up with 30 000 hard coded strings. Further analysis reveals that out of these 30 000 hard coded strings around 10 000 are part of macros and do not need to be externalized. So we are left with 20 000 hard coded strings which probably need to be externalized. In this example exercise context it is concluded that around 40 of the detected strings need to be externalized. This number can still be reduced as more detailed code inspection is done but for the purpose of estimation it gives a fair level of accuracy.

Sometimes if manual code inspection is not possible the sampling percentage can be taken by analyzing samples of the code taken from the entire source code. One can come up with some statistics based on the sample files analyzed. The accuracy of this statistic depends on how well the sample is chosen. The sample files taken must contain enough internationalization impact areas in order to be a representative sample. The estimation model defines the following approach for such cases 

The internationalization code analysis tool can be executed on the entire code base C C Java or the like . This will give an overall statistic regarding the internationalization readiness of the application and give a breakup of the modules and files impacted most.

Files containing the source code with candidate internationalization impact points can be selected from each of the components modules present in the application for sampling. A combination of Systematic and Stratified sampling can be used to take the sample. The discussion of sampling herein provides more details.

The sample files can be analyzed manually to determine the actual number of internationalization impact points in those files. Taking into account the total number of impacted files that data can then be extrapolated to obtain a percentage of actual impact points out of the numbers reported by the internationalization analysis tool.

Accurate sampling depends on the quality of sample files chosen. More details on the data sampling approach are described herein.

SIEM can be based on quantitative and qualitative inputs to derive the effort estimation. Typical mature organizations keep a record of staff productivity figures for various programming languages e.g. in terms of SLOC per day function points per day or the like . Apart from this industry data on such productivity figures is also available. Taking the historical data it is possible to estimate for internationalization changes if what kind of changes are expected to be done in the code are known.

Unlike regular maintenance projects where the specific changes to the code cannot be estimated initially when we analyze the code for internationalization changes we know specifically what code needs to be changed from experience of internationalization projects executed in the past one knows approximately how many lines of code will be taken to complete the change. Internationalization changes mainly involve externalizing hard coded strings and replacing non Unicode functions and data types with their Unicode equivalent. This can be a simple but laborious activity as the number of hard coded strings and non Unicode may be in thousands. If the specific number of such occurrences can be counted one can use this information along with the productivity figures for the particular language and come to a reasonable estimate to make the changes.

Most of the above inputs are quantitative in nature and can be obtained using static analysis tools. An internationalization analyzer tool can be used to get most of the above inputs. Apart from this there may be other inputs which are application specific e.g. creation of internationalization wrapper library creation of special UI elements data migration etc. . In order to estimate the internationalization impact for such requirements one can rely on past experiences with making similar changes in products with related technologies and programming languages. These estimation figures are qualitative in nature and may vary depending on the product team dynamics programming language platform etc.

For all the quantitative data put into the SIEM template the effort can be calculated by taking into consideration the productivity figures of the organization historical data and the SLOC to implement one unit of the internationalization impact point. More details on the effort modeling approach are described herein.

For the qualitative inputs the estimation model relies on estimation by analogy to arrive at an approximate effort. The approach generally followed is as follows 

Like most projects an internationalization project can have the different life cycle phases e.g. analysis design build testing etc. . The estimation model can take into account such SDLC phases project management configuration management and other miscellaneous activities in order to calculate the overall effort. The effort distribution as per process capability baseline can be used as the basis for overall effort calculation.

Sampling can be done as part of data collection. Sampling can include a statistical way of analyzing the subset of a large population in order to make some conclusions about the entire population itself. The techniques can include a selection of a good sample which is representative of the whole population in terms of its characteristics. The approach can be applied during internationalization analysis to do an effort estimate for internationalizing the entire source code by analyzing a few sample source files which are impacted by internationalization changes.

Internationalization analysis of an existing application product can involve analyzing the source code to check the current level of internationalization and detect gaps that need to be addressed in order to make the code fully internationalized. Some of the major internationalization impact areas e.g. candidate internationalization impact points in the code are as follows 

These are string literals that are hard coded into the code itself. They are present as part of user visible alerts log messages static UI labels etc. Any change in the strings can lead to a recompilation of the source code.

For the code to be internationalized hard coded strings e.g. at least those which are user visible need to be externalized e.g. to a properties or resource file .

These are APIs and functions that only support single byte data ANSI ASCII . A majority of such APIs e.g. strcmp strcpy etc. work on single bytes only and are not able to handle Unicode data.

For the code to be internationalized non Unicode APIs and functions need to be replaced with their Unicode equivalent APIs. e.g. wcscmp wcscpy etc. . Not all non Unicode APIs need to be replaced. It also depends on the target encoding to be supported. e.g. strcpy may work for UTF8 but needs to be replaced with wcscpy for UTF16. 

For the code to be internationalized non Unicode data types need to be replaced with their Unicode equivalent data types e.g. wchar t wstring etc. . Not all non Unicode data types need to be replaced. It also depends on the data being processed. If it is known that the data for a particular module will not be Unicode those data types need not be replaced.

When an application has to be supported in multiple regions the application should be able to display date and time values in the users local format.

Accordingly the impact of time zone can be taken into account for date time fields by using the appropriate date time formatting functions.

Different regions have different formats of representing numbers. The symbols used for decimals and thousand separator can vary.

For the code to be internationalized the application needs to be able to set the number format as per the locale in which it is running.

Typically most non internationalized applications have to address the above impacted areas along with many others in order to attain some level of internationalization. As part of effort estimation for internationalization requirements one can start with analyzing the source code in order to collect raw data regarding the internationalization impact areas. This can include manual review of the code which may be a very time consuming activity if the source code is large. The code analysis can be expedited by the use of internationalization analysis tools. The output of such a tool can be a report that lists the instances of hard coded strings non Unicode APIs and data types date formatting number formatting etc. apart from other impact points.

During internationalization analysis exercises it was discovered that hard coded strings and non Unicode APIs data types form the bulk of impacted areas in the code. Past experience also indicates that not all instances of hard coded strings or non Unicode APIs data types need to be changed in order to internationalize the code. For any medium to large application their numbers are in thousands and it is virtually impossible to analyze each hard coded string or API to check if they really need to be changed in the internationalization context. Consequently the effort estimation for internationalization changes becomes difficult since the volume of impacted areas to be analyzed is huge. For such scenarios a data sampling approach can be taken to come up with an effort estimate based on a sample of the impacted code. The sample chosen can be a good representative of the entire source code in order to get a good estimate.

As part of internationalization analysis the following steps can be followed while sampling internationalization data 

This gives a list of files containing hard coded strings along with the count of hard coded strings in each file. The list can be sorted by the number of hard coded strings in the files.

This gives a list of files containing non Unicode APIs along with the count of non Unicode APIs in each file. The list can be sorted by the number of non Unicode APIs in the files.

This gives a list of files containing non Unicode data types along with the count of non Unicode data types in each file. The list can be sorted by the number of non Unicode data types in the files.

The impact points under consideration are hard coded strings and non Unicode APIs data types since they form the bulk of impact points for analysis. However analysis can be done on other impact points too e.g. if they are in very large numbers .

Ordered list of files based on each specific impact point e.g. ordered list of files based on the occurrences of hard coded strings non Unicode APIs data types as shown below.

Sampling can start with identifying the sampling source. One can identify the source from which the sample will be drawn. A preliminary analysis of the source code structure along with the internationalization analysis report generated by the internationalization analysis tool can help in the selection. Looking at the density of internationalization impact points number of impact points per file throughout the code the samples can be taken from some particular modules folders etc.

For the internationalization analysis the entire source code can be considered as the sampling source.

The sampling frame can be the list of all elements in the population of interest. The sampling frame can define the target population from which the sample is drawn and to which the sample data will be generalized.

For the internationalization analysis the sampling frame will be the files in the source code which contain the internationalization impact points as indicated by the internationalization analyzer tool.

Picking a quality sample can be supported. The sample selected should contain the right mix of internationalization impact points so as to form a representative of the entire source code.

There are a number of sampling methods that can be used such as simple random sampling SRS Systematic sampling Stratified sampling Cluster sampling etc. Different methods have their own advantages and disadvantages. One can select the method that works best in the internationalization analysis exercise. For the internationalization sampling exercise a mix of systematic sampling and stratified sampling techniques can be used.

As per the stratified sampling method each individual report obtained above can be considered as a separate population stratum for the sampling exercise. Segregating the entire population may be an expensive and time consuming exercise but the internationalization analysis tool can allow automation and can provide reports that are in the needed format for data sampling.

Systematic sampling can then be applied to each stratum. Systematic sampling can ensure that all files in the source code have equal probability of being selected. Because samples are taken from different strata e.g. hard coded strings non Unicode APIs non Unicode data types and the like varying in size it provides a balance while analyzing the entire source code by taking into account the variance in impact points across the entire source code.

Sample size calculation is concerned with how much data needs to be analyzed in order to draw conclusions about the whole population. Determination of an appropriate sample size can be a statistical exercise. If the sample size is too small it may not yield accurate results while a large sample size will result in wasting time though it leads to increased precision in estimates.

In the case of internationalization analysis one might have thousands of internationalization impact points hard coded strings non Unicode API s etc. in the code. Because it is not always feasible to analyze all the impacted source files one can select a certain number of files from the whole source code from which one can extrapolate the results and draw some conclusions.

For most statistical calculations a margin of error of 5 and a confidence level of 95 gives a fairly good level of approximation.

The distribution of standard scores has a Mean of 0 and a standard deviation of 1. Using the standard deviation tables one can calculate the standard score for the cumulative probability calculated above mean of 0 and standard deviation of 1. This calculation is based on the standard normal distribution table. For example for a confidence level of 95 the cumulative probability is 0.975 for which the z score from the standard normal distribution table is 1.96.

What this basically means is that if one finds that 15 of the hard coded strings in the sample are supposed to be externalized with a precision rate of 5 one can conclude that between 10 and 20 of the hard coded strings from the total hard coded strings would have to be externalized. So it gives a range taking into account the margin of error. One can accordingly choose the best worst case scenarios.

Using the above a sample size can be obtained which helps in selecting a sample from the entire source code for the purpose of the analysis.

After the reports on the internationalization impact points are obtained from the internationalization analysis tool the reports can be analyzed in order to determine the sample files that need to be considered for detailed analysis.

Assume the source code has 5000 files. As per the internationalization analysis 2500 files are found to contain internationalization impact points out of which 2000 files are found to have hard coded strings 1500 files are found to have non Unicode APIs and 1700 files are found to have non Unicode data types as shown in the tables herein.

As per the stratified sampling technique one can divide the population 5000 files into 3 parts the files containing the hard coded strings the files containing the non Unicode APIs and the files containing the non Unicode data types. These 3 parts will be regarded as our strata.

After the sample size for each stratum is obtained samples can be taken from each stratum using the systematic sampling method e.g. depending on the sample size . Files are selected at regular intervals from each stratum.

For example as per the figures calculated above systematic sampling will be done based on the following sampling intervals rounded to the next whole number 

After this exercise a total of 942 sample files will be available for detailed analysis. It is quite possible that some files may contain a mix of hard coded strings non Unicode APIs and non Unicode data types. One can safely assume that they would be representative of the entire source code and would contain enough variance to enable one to make extrapolations on the sample.

The sampled files are representative of the entire source code. These sample files need to be analyzed further to check if the candidate internationalization impact points are in fact required to be fixed in order to internationalize the code e.g. are true impact points . Detailed analysis of the sample can be done using the analysis tool or by manually scanning the code.

Filtering out internationalization impact points which need not be changed can be based on a number of factors. Some typical scenarios are as follows 

For each file analyzed each impact point in that file can be tagged as impacted or not impacted. Once the samples have been analyzed typically the result of the detailed analysis should be as follows 

From this sampling analysis one can conclude that around 15 of the total hard coded strings need to be externalized around 40 of non Unicode APIs need to be replaced with their Unicode equivalents and around 35 of non Unicode data types need to be replaced with their Unicode equivalents.

These figures can be used in the Software Internationalization Estimation Model in order to arrive at more accurate estimates.

Systematic sampling can arrange the population according to some ordering scheme and then select samples from regular intervals e.g. starting at some random element every subsequent nth element is selected in the sample where n population size sample size . In practice the starting element is not the first in the list but chosen randomly between the first and nth element.

To implement stratified sample when the population has a number of different categories the population itself can be divided into a number of different strata where each stratum can be sampled as a separate sub population out of which elements can be randomly selected individual estimates per strata can be made and then combined.

Margin of error can also be called the Confidence interval. It is the amount of error that one can accept in the sampling calculation. The margin of error selected depends on the precision needed to make population estimates from a sample.

For example while analyzing hard coded strings in the source code the margin of error might be or 3 . This means that if 60 of the hard coded strings in a sample are to be externalized one could be confident that if one analyzed the entire source code between 57 60 3 and 63 60 3 of the hard coded strings would have to be externalized.

Confidence level is the amount of uncertainty that one can accept in the sampling calculation. It is the estimated probability that a population estimate lies within a given margin of error. When one says confidence level is 95 one is saying that 95 out of 100 samples are a good representative of the entire population within the level of precision defined.

For example a confidence level of 95 indicates that one can be 95 confident that between 57 and 63 of the hard coded strings have to be externalized.

Population size is a measure of the number of elements from which the sample can be chosen. The sample size typically does not change much for populations greater than 20 000.

An effort modeling approach can be included as part of the Software Internationalization Estimation Model. The approach can be a quantitative way of calculating the internationalization effort for one unit of a particular internationalization impact point e.g. the effort required to externalize one hard coded string . The approach can involve assessment of the change needed for a given internationalization feature coupled with the development productivity data to calculate the effort needed for one unit of the given internationalization feature. The approach can provide the internationalization productivity figures or the effort needed for one unit of work. The correctness of overall effort estimation can be supported by the data obtained from sampling which represents the total number of units of work and or knowledge regarding the code changes required.

Different software estimation models techniques can use different models approaches to define a unit of work and the effort for that unit of work. For example a work break down model can define units as simple medium complex and then assign effort for each unit. A Function Point technique can define one function point as the smallest unit of work and then assign effort to this unit.

A model can be based on quantitative data and can provide more accurate effort estimates. The model can derive the effort needed for a unit work from the Function Point technique and a Process Capability matrix.

Identify the effort needed for one Function Point from a Process Capability matrix PCB . The PCB can contain productivity figures based on different projects of similar type of work and similar technologies that are executed within the organization in the last couple of years.

One function point is then mapped to the lines of code based on a software language productivity table e.g. Caper Jones or the like .

The number of lines of code to be changed can be derived from the implementation approach for that feature in the respective programming language. For example externalizing a hard coded string might take 2 lines of code in Java and 4 lines of code in C .

Use the information from the above to calculate the amount of effort needed for one unit of internationalization feature.

These are string literals that are hard coded into the code itself. They are present as part of user visible alerts log messages static UI labels etc. Any change in the strings can lead to a recompilation of the source code.

For the code to be internationalized hard coded strings e.g. at least those which are user visible need be externalized to a properties or resource file. The code can then use Resource Bundle APIs to fetch the localized message at runtime.

In a normal scenario around 3 lines of code change can replace a hard coded string with a ResourceBundle call in Java. So externalizing 18 to 19 hard coded strings would constitute 1 function point in Java.

These are APIs and functions that only support ASCII data. A majority of these APIs e.g. strcmp strcpy etc. work on single bytes and are not able to handle multi byte data.

For the code to be internationalized non Unicode APIs and functions need to be replaced with their Unicode equivalent API e.g. wcscmp wcscpy etc. .

Replacing Non Unicode compliant API with a Unicode Compliant API varies from programming language to language.

In most of the cases around 4 or 5 lines of code change can replace a non Unicode API with a Unicode API in C which implies changing 13 to 15 Non Unicode APIs to Unicode APIs constitutes one function point in C .

When an application has to be supported in multiple regions it is important that the application be able to display date and time values in the local format.

Accordingly the impact of time zone needs to be taken into account for date time fields by using the appropriate date time formatting functions.

In a normal scenario around 3 lines of code can implement locale specific Date time formatting in Java which implies 18 to 19 date time formatting changes would constitute 1 function point in Java.

Different regions have different formats of representing numbers. The symbols used for decimals and thousand separator can vary.

For the code to be internationalized the application needs to be able to set the number format as per the locale in which it is running.

In a normal scenario around 3 lines of code change can implement locale specific number formatting in Java which implies 18 to 19 number formatting changes would constitute 1 function point in Java.

On similar lines size of code change for different internationalization features in a given programming language are obtained based on their most appropriate implementation details.

Typically most non internationalization applications have to address the above impacted areas along with many others in order to attain some level of internationalization. As part of effort modeling based on high level approach the size of work is determined which is then used to identify the effort estimate for that requirement.

Individuals or organizations can define their productivity figures. Also lines of code may differ from implementation to implementation. The above calculations can be done taking these variables into account.

The following demonstrates the exemplary use of an Effort Modeling Approach to calculate the effort for one unit of ResourceBundle change in Java.

Referring to the process capability matrix data for Productivity data for maintenance projects in a high level language e.g. Java C the average productivity figure for a major enhancement is 44 FP PM Function Point per Person Month .

One can refer to a software language productivity table e.g. Caper Jones or the like to map size of code in terms of Lines of Code with Size in terms of FP. So for Java 1 FP is equivalent to 53 Lines of code.

For 1 simple resource bundle change on average around 3 lines of code change addition modification is needed.

Above mentioned data is then used to calculate the effort needed for one unit of Resource Bundle change. The table below shows exemplary calculations 

A PCB for maintenance projects with major enhancements is shown below and can be referred to for the productivity figures. The matrix can be based on historical data for an organization or other unit of observation over a particular time period.

Margin of error This is also known as the Confidence interval. It is the amount of error that one can accept in the sampling calculation. The margin of error selected depends on the precision needed to make population estimates from a sample. This can generally be taken as 5 .

Confidence Level Confidence level is the amount of uncertainty that one can accept in the sampling calculation. It is the estimated probability that a population estimate lies within a given margin of error. When one says confidence level is 95 one is saying that 95 out of 100 samples are a good representative of the entire population within the level of precision defined.

Total files containing hard coded strings These are string literals which are hard coded into the code itself. They are present as part of user visible alerts log messages static UI labels etc.

Enter the number of files containing hard coded strings as per the report generated by an internationalization analyzer tool.

Total files containing non Unicode APIs These are APIs and functions which only support single byte data ANSI ASCII . Enter the number of files containing non Unicode APIs as per the report generated by an internationalization analyzer tool.

Total files containing non Unicode data types These are data types which typically handle only single byte data. Enter the number of files containing non Unicode data types as per the report generated by an internationalization analyzer tool.

The template can then calculate the sample size. In the interim calculations a can be calculated as 1 confidence level .

The different sample sizes can be used in a stratification scenario as described herein. In practice additional and or different strata can be used in the template.

The techniques and solutions described herein can be performed by software hardware or both of a computing environment such as one or more computing devices. For example computing devices include server computers desktop computers laptop computers notebook computers handheld devices netbooks tablet devices mobile devices PDAs and other types of computing devices.

With reference to the computing environment includes at least one processing unit coupled to memory . In this basic configuration is included within a dashed line. The processing unit executes computer executable instructions and may be a real or a virtual processor. In a multi processing system multiple processing units execute computer executable instructions to increase processing power. The memory may be volatile memory e.g. registers cache RAM non volatile memory e.g. ROM EEPROM flash memory etc. or some combination of the two. The memory can store software implementing any of the technologies described herein.

A computing environment may have additional features. For example the computing environment includes storage one or more input devices one or more output devices and one or more communication connections . An interconnection mechanism not shown such as a bus controller or network interconnects the components of the computing environment . Typically operating system software not shown provides an operating environment for other software executing in the computing environment and coordinates activities of the components of the computing environment .

The storage may be removable or non removable and includes magnetic disks magnetic tapes or cassettes CD ROMs CD RWs DVDs or any other computer readable media which can be used to store information and which can be accessed within the computing environment . The storage can store software containing instructions for any of the technologies described herein.

The input device s may be a touch input device such as a keyboard mouse pen or trackball a voice input device a scanning device or another device that provides input to the computing environment . For audio the input device s may be a sound card or similar device that accepts audio input in analog or digital form or a CD ROM reader that provides audio samples to the computing environment. The output device s may be a display printer speaker CD writer or another device that provides output from the computing environment .

The communication connection s enable communication over a communication mechanism to another computing entity. The communication mechanism conveys information such as computer executable instructions audio video or other information or other data. By way of example and not limitation communication mechanisms include wired or wireless techniques implemented with an electrical optical RF infrared acoustic or other carrier.

The techniques herein can be described in the general context of computer executable instructions such as those included in program modules being executed in a computing environment on a target real or virtual processor. Generally program modules include routines programs libraries objects classes components data structures etc. that perform particular tasks or implement particular abstract data types. The functionality of the program modules may be combined or split between program modules as desired in various embodiments. Computer executable instructions for program modules may be executed within a local or distributed computing environment.

Any of the computer readable media herein can be non transitory e.g. memory magnetic storage optical storage or the like .

Any of the storing actions described herein can be implemented by storing in one or more computer readable media e.g. computer readable storage media or other tangible media .

Any of the things described as stored can be stored in one or more computer readable media e.g. computer readable storage media or other tangible media .

Any of the methods described herein can be implemented by computer executable instructions in e.g. encoded on one or more computer readable media e.g. computer readable storage media or other tangible media . Such instructions can cause a computer to perform the method. The technologies described herein can be implemented in a variety of programming languages.

Any of the methods described herein can be implemented by computer executable instructions stored in one or more computer readable storage devices e.g. memory magnetic storage optical storage or the like . Such instructions can cause a computer to perform the method.

The technologies from any example can be combined with the technologies described in any one or more of the other examples. In view of the many possible embodiments to which the principles of the disclosed technology may be applied it should be recognized that the illustrated embodiments are examples of the disclosed technology and should not be taken as a limitation on the scope of the disclosed technology. Rather the scope of the disclosed technology includes what is covered by the following claims. We therefore claim as our invention all that comes within the scope and spirit of the claims.

