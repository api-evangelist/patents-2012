---

title: Web page performance scoring
abstract: A browser-based tool is provided that loads a Webpage, accesses the document object model (DOM) of the page, collects information about the page structure and parses the page, determines through the use of heuristics such factors as how much text is found on the page and the like, produces statistical breakdown of the page, and calculates a score based on performance of the page. Key to the operation of the invention is the ability to observe operation of the Webpage as it actually loads in real time, scoring the page for several of various performance factors, and producing a combined score for the various factors.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08768918&OS=08768918&RS=08768918
owner: Mercury Kingdom Assets Limited
number: 08768918
owner_city: Road Town, Tortola
owner_country: VG
publication_date: 20120413
---
This application is a divisional application of U.S. patent application Ser. No. 13 290 897 filed Nov. 7 2011 the entirety of which is incorporated herein by this reference thereto.

U.S. patent application Ser. No. 13 290 897 is a continuation of U.S. patent application Ser. No. 12 262 054 filed Oct. 30 2008 now U.S. Pat. No. 8 078 614 which is a continuation of U.S. patent application Ser. No. 10 887 956 filed Jul. 9 2004 now U.S. Pat. No. 7 475 867.

The invention relates to a global telecommunications network. More particularly the invention relates to a tool which analyses the content and structure of Web pages in real time and produces statistics and a performance score.

Web page performance affects the quality of experience for visitors as well as server performance requirements. Web page performance depends upon many factors such as the number and sizes of files required to display the page the organization of the page the result of any modifications to the page performed by script and the configuration of the Web server s hosting the content.

WebSiteOptimization.com see offers a product which is designated Web Page Analyzer 0.82. In using this product a user enters a URL into a field within a Web page form to invoke a script that accesses the Web page associated with the entered URL. The script calculates Web page size composition and download time . The script also calculates the size of individual elements and finds the total for each type of Web page component . Based on these page characteristics the script then offers advice derived from anecdotal evidence and prior experience on how to improve page display time.

While determining file sizes can be accomplished relatively easily determining the actual page content the effects of the page structure and server configuration is more difficult. Such determination typically requires reliance upon experimental data that depends upon the availability of network connections of varying speeds as is the case with Web Page Analyzer 0.82.

It would be advantageous to provide a Web developer with the means to determine the relative performance of a Web page quickly without having to rely upon experimental and anecdotal data that also depend upon the availability of network connections of varying speeds.

The invention comprises a tool that provides a Web developer with the means to determine the relative performance of a Web page quickly in real time without having to rely upon experimental and anecdotal data that is also dependent upon the availability of network connections of varying speeds. Deployment and use of this tool as a means of measuring and enforcing coding techniques which improve Web page performance can potentially provide a competitive advantage over competitor Web sites which do not optimize their content for performance.

The presently preferred embodiment of the invention comprises a browser based tool that loads a Web page accesses the document object model DOM of the page collects information about the page structure and parses the page determines through the use of heuristics such factors as how much text is found on the page and the like produces a statistical breakdown of the page and calculates a score based on performance of the page. Key to the operation of the invention is the ability to observe operation of the Web page as it actually loads in real time scoring the page for several of various performance factors and producing a combined score for the various factors. It is also possible to operate the invention such that it runs without user interaction and observation for example on a server.

The invention comprises a tool that provides a Web developer with the means to determine the relative performance of a Web page quickly in real time without having to rely upon experimental and anecdotal data that is also dependent upon the availability of network connections of varying speeds. Deployment and use of this tool as a means of measuring and enforcing coding techniques which improve Web page performance can potentially provide a competitive advantage over competitor Websites which do not optimize their content for performance.

One embodiment of the Web page scoring tool disclosed herein provides a method of calculating a score which is a measure of the potential page load performance of the pages in a Web site for visitors with varying network performance characteristics.

The tool can visit either a single page or all pages linked from a page up to a specified depth while providing scores overall statistics and details for each included file.

The tool is designed to be run as a Web page using a browser such as the Netscape Gecko based browser. In the embodiment that comprises a Netscape Gecko based browser XPConnect is used to obtain information from the browser s cache regarding the files included by a Web page.

The tool must first load the page or pages to be analyzed. Once the pages have been loaded various reports can be generated for different network and user parameters without having to load the pages again.

Choose a depth for the tool to follow links from the starting URL. A depth of 0 only loads and analyzes a single page. A depth of 1 analyzes the starting page and all pages linked to from the starting page.

Choose whether to restrict Urls. Restricting Urls prevents the tool from following any link which does not begin with the starting url. For example if the starting Url is http cnn.com and all links begin with http www.cnn.com then the tool does not follow the links if Restrict Url is checked.

Choose a page timeout value. This value in seconds is the time the tool waits for a page to load before timing out and entering the pause state.

If it is desired to save the parameters in the form of a Url which can be reused in the form of a hyperlink click Save Parameters which creates a Url in the browser s location bar which has be saved.

While it is running the tool provides feedback on which page is currently being loaded and how many pages have been loaded so far as well as how many pages remain to be loaded.

Once the tool has finished loading all pages the reports can be generated. The scores reported by the tool depend upon the values entered for the network and visitor parameters. It is possible to run the reports with differing parameters without having to re load and re analyze the pages each time.

The actual page load performance of a Web page depends upon the visitor s network connection. The network parameters allow the user to calculate scores for the various types of visitor expected such as dialup Cable DSL broadband or Satellite broadband.

Enter the bandwidth in Bytes Second of the visitor s connection. A typical dialup visitor using a 56 kbps modem might have a bandwidth of 4096 Bytes Second.

Enter the modem compression factor available to the visitor. A value of 1.0 means no compression while a factor of 0.25 means the modem is able to compress text to 25 of its original size. Cable DSL Satellite broadband visitors typically have no compression and this value should be set to 1.0

Enter the time in seconds for the visitor s client to perform a DNS Lookup. Typical values for dialup users are on the order of 0.5 to 1.0 second for Cable DSL broadband on the order of 0.1 to 0.7 second while Satellite broadband may see values in excess of 1.5 to two seconds.

Enter the time in seconds for a ping to travel from the visitor s machine to the Web server and back. Typical values for a dialup user are on the order of 0.3 seconds Cable DSL broadband on the order of 0.1 seconds while Satellite broadband may see values in excess of 1.5 seconds.

Due to the high latency implicit in Satellite broadband Web pages which score well for dialup or Cable DSL visitors may have an extremely poor score for Satellite broadband visitors. Approximately 30 million homes in the United States as well as many others in other countries do not have the option of using Cable or DSL broadband. Optimizing content for Satellite broadband visitors is an important consideration.

The perceived performance of a Web page depends upon the user s behavior e.g. how often the visitor returns to the page how long does the visitor spend on page before clicking on a link and how much time they consider it reasonable for a page to load.

Enter the Revisit Time in seconds which measures how often a visitor returns to a page. This value is used to determine which files have unexpired cache entries when the visitor returns.

Enter the IntraPage Time in seconds which measures how long the visitor views a page before clicking on a link. This value is used to determine which files have unexpired cache entries when visiting links and is used to calculate a score for each page a visitor may click once the original page has loaded.

Enter the Perception Time in seconds which is used to measure the impatience of a visitor. A dialup user may be more tolerable of slow loading pages than a broadband visitor. A value of ten seconds for a dialup visitor is reasonable while a value for a Cable DSL broadband user may be much less.

Once all reporting parameters are entered the user can either click on Report or Save Report to generate a report. To generate multiple reports on the same Web page s using different parameters simply change the report parameters and click either Report or Save Report again.

The Report button dynamically creates a report in a new window. This option is quick and simple however it does not create a window that can be saved or forwarded to another user. To save a report in a format which can be saved locally or forwarded to another user click the Save Report button. If the user clicks the Save Report button a hyperlink appears in the message pane when the report is ready. Click on the link to open a new window which can be saved locally forwarded in email etc.

Results are not absolute and must be interpreted. What works for one visitor may not work for another. For example a dialup user with slow download speeds but relatively fast DNS Lookup and Ping times may find that a page which uses external files for scripts and CSS performs better than one without. On the other hand a satellite broadband user with high download speeds and slow DNS Lookups and Ping times may find that a page which uses inline Script and CSS performs much better than the equivalent page using external files. Use these reports appropriately for the site in question and expected audience.

One of the most important influences of a Web page s performance is due to the caching configuration of the Web servers. Appropriately cached files do not require network traffic and improve both the experience of dialup as well as satellite broadband users.

The Parameters section of the report shows the values use to calculate the scores for the pages. Individual scores must be interpreted with these parameters in mind because the same page may have widely varying scores depending upon the parameters chosen.

Each page report begins with Page url Score value. The score is the value for the total First Visit score which assumes that no files have been cached and includes the time to download all content for the page.

The Page Scores table provides a breakdown of the scoring for a page by First Second visit versus Blocking Total.

The First Visit score assumes the visitor has not been to the site before or that their cache has been emptied. The Second Visit score assumes the visitor has previously visited the page and is revisiting after the time specified by the Revisit Time parameter. Comparing First Visit to Second Visit scores can indicate the effectiveness of the caching strategies in use on the site.

First and Second Visit scores are also broken down by Blocking versus Total. The Total Score is calculated from the time required to load all files required by the page. The Blocking score is calculated solely from files which may potentially block the display of a page until they have been downloaded. Blocking scores are intended to give a measure of how quickly the user experiences some feedback that the page is loading.

The Notes section contains comments which are intended to indicate that improvements may be possible with further investigation.

The Summary Statistics section contains summary information regarding the Web page such as if the document is compressed the total size number of domain lookups which may be required etc.

The File Cache Data section follows the Summary Statistics section and contains detailed cache information for each file included in the Web page. The HTTP Header is in red if the date reported by the Web server are more than an hour different from the time the page was analyzed. This can be useful in ensuring that the Web server s dates are properly set.

If Depth was set to greater than 0 the Link Section of the report lists each link found on the page along with an effective score which measures the time required to load the linked page once the original page s content has been loaded. These scores can be used to determine the benefit of caching common files across a site.

The following reports were generated for CNN.com using a dialup K modem with a 40 kbps connection using identical Visitor parameters revisit after one day while varying the Network parameters.

Because each example report uses the same Perception Time value of ten seconds these reports imply that that it takes a Dialup visitor approximately 50 seconds to load CNN the first time a Cable visitor 20 seconds and a Satellite visitor over 130 seconds.

These reports also indicate that for visitors who only visit CNN once per day caching provides no benefit for their first visit of the day.

The Web page scoring tool uses the time to perform DNS lookups round trip time for requests download size and bandwidth and the blocking nature of external CSS and JavaScript files to determine a calculated download time. This download time is scaled by the Visitor Perception Time parameter to determine a score.

While the report shown in includes the various factors identified above those skilled in the art will appreciate that the invention may provide reports in any other format as desired including such factors as may be of interest.

Key to the operation of the invention is the ability to observe operation of the Web page in real time as it is loading further determine performance after a second cached load score the page for several of various performance factors and produce a combined score for the various factors .

One presently preferred embodiment of the invention comprises a tool that has been implemented as a special Web page hosted in a Netscape 7.0x Mozilla see http channels.netscape.com ns browsers default.jsp sidebar. The tool uses a JavaScript see http devedge.netscape.com central javascript ECMAScript see http www.ecma international.org publications standards ECMA 262.HTM Standard Ecma 262 ECMAScript Language Specification 3rd edition December 1999 standards based mechanism for access to the Web page document structure by means of the W3C DOM see http www.w3.org DOM application programming interface as well as access to internal services exposed by the Netscape 7 Mozilla browser to access file cache and size information.

The tool is readily extended to operate using Netscape 7 Mozilla in batch mode for automated reporting. Implementations in Perl see http www.perl.com are also currently being considered.

Further those skilled in the art will appreciate that any other browser e.g. Microsoft s Internet Explorer may be used in connection with the invention disclosed herein. Thus the tool is readily implemented in different environments if the following components normally found in a Web browser are available 

Although the invention is described herein with reference to the preferred embodiment one skilled in the art will readily appreciate that other applications may be substituted for those set forth herein without departing from the spirit and scope of the present invention. For example the invention allows the scoring of cached vs. uncached versions of a page. Additionally the invention is readily implemented in a system the does not comprise a browser e.g. in PERL etc. It is also possible to operate the invention such that it runs without user interaction and observation for example on a server.

