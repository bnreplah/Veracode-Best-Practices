# Dynamic Best Practices #


## TLDR ##
### DAST Essentials ###
Start with a prescan, quick scan , then full scan, then add authentication, then look at allowed and denied urls to strict and expand scope


## How it works ##

Veracode Dynamic Analysis interacts with the application like an attacker. It starts by performing a crawl to understand the application’s architecture, including links, text, form fills, and other page elements that a user could potentially interact with. It also picks up on attack points that are less visible to the user, such as header values, cookies, and URL parameters. The scanner then audits the objects and attributes discovered by the crawl and sends attacks – like Cross-Site Scripting and SQL Injection – to the objects/attributes to see if they have any exploitable vulnerabilities.


Today’s web applications are complex and full of features and functions for users to interact with. Likewise, a dynamic analysis crawler will not only need to interact with the application in the desired way, but will also exercise each part of the application with payloads that test for vulnerabilities. 


Veracode Dynamic Analysis scan engine is designed to test production web applications with minimal impact, and uses testing approaches that do not harm the site or accidentally delete data. The more complex a web application is, the more requests and permutations of tests will be required, which take time to complete.


This document outlines several approaches to optimizing the scan configuration in order to provide a comprehensive audit of your web application.


## Review scan coverage report ##
Unless you are keenly aware of the exact structure and functionality of your web application, the first scan should be treated as a reconnaissance analysis. Initially, a Dynamic Analysis scan should be run without many guardrails, so that it can freely explore your web application and populate the Coverage Report with as much detail as possible. 


Once you have completed the initial scan, you can begin to review the Coverage Report. The Coverage Report provides a wealth of information with regards to what the scan engine’s experience was during an automated crawl of your web application. Within the Scan Coverage report, you can begin to see patterns of behavior and take steps to help optimize the scan configuration. 


### Eliminating Redundant Content ###
One of the major outcomes of reviewing the Coverage Report is to further enhance the built-in redundancy checks of the scanning engine to account for the uniqueness of your web application. Veracode Dynamic Analysis has built-in redundancy checks and will recognize similar content as it traverses throughout the web application. However, some we applications create content in such ways where only a human can determine that the same code functionality is driving the presentation layer.


### Inform the scan engine of similar content: ###
As patterns emerge during review of the Coverage Report, you can note these down and use the Allowlist and Blocklist functionality to enter in  

use the allowlist and blocklist feature to remove duplicate pages/content


### Links to tracking sites and ad servers: ###
Many of today’s web applications include links to elements used to track user behavior and provide a wealth of information to marketing and analytics teams. However, these can also create a lot of noise for automated crawlers which will “see” all these links and still perform a GET request while they initially load each page for further inspection. While in almost all cases there is no need to do take any action on these types of links, in some cases there can be so many of these trackers that can in fact contribute to the time it takes to scan a web application. If you notice an over abundance of links to various external trackers and even ad serving URLs, take note of the most common domains


In general the amount of 3rd party traffic is not related to time spent scanning. The browser itself and customer apps have 3rd party content and it is requested as part of the scanning process. More often in cases like this, the real problem is related to automated content generation i.e. we generate content on the site in a way that fools the dupe check so we keep seeing everything as "new". At the moment, we unfortunately don't expose any of the controls that can be used to combat this, but there are some settings an internal operator can tweak to adjust this. Most directly, there is a alternate detection scheme from default that uses the URL in the browser window to determine uniqueness. This sometimes is a better fit and can help scans go faster. Also, with the default setting there is a similarity threshold that is set to .95 by default lowering this to .90 or .85 often helps the dedupe algorithm drop content more reliably. This setting is truly never one-size-fits-all anyway, so some adjustment to it is often beneficial.

I do hope someday we can expose these settings, along with details on how they work, so an advanced user could make these adjustments themselves, but for now it would probably need a support ticket to investigate further or make adjustments.

### Links to disruptive areas of the web application: ###
delete/reset, delete user, can sometimes be available via a simple link to high-priveleged users. Ensure the test account used for scanning does not have this type of access or specifically block the functionality.

With API specification scans, you can control which endpoints will be auditted. You should review and remove any endpoints that may cause some destructive behavior.

## Expand the scope of the scan ##
While we focused on areas where the scan engine explored too much of the site and increased scan time, there are instances where it may have missed areas of the web application due to too narrow of a scope defined.

### Subdomains ###
Take, for example, a site that includes subdomains… if they are in scope, add them to the allowlist so that the crawler can transition from one subdomain to another when it encounters a link to that content. This is particularly useful if you wish for a single report encompassing a full web application.

### Directories and Subdirectories ###
Take note of the “Directory, Directory and subdirectory” scan settings. In some instances, the content you may wish to scan is organized by directory on the same root domain. 


## Improve Network connectivity ##
In some cases, the responsiveness of the target web application can impact the duration of the overall scan. Keeping the following considerations in mind can help with a faster scan time. 

First, schedule the scan during low load-times so the site can respond quicker to the many requests Dynamic Analysis will be sending. Remember that unlike a human user, the Dynamic Analysis engine will send multiple requests to the same resource as it performs various tests.

Second, if using Veracode Internal Scan Management (ISM), place the ISM as close to target application as is possible. For example, install ISM in same datacenter or network segment as target app to decrease the number of hops required to reach the target application.

## Authentication Best Practices ##
Veracode Dynamic Analysis is often used to test applications which require authentication. Many authentication methods are support and well documented in the Veracode Help Center. To help eliminate scan failures or scans with little or no coverage when scanning authenticated sites, there are a few best practices to keep in mind.

`Test credentials`: do not use personal real credentials. The crawler will login with these and use them to perform testing. It is best to use test credentials created specifically for scanning purposes.

`Password lock out`: If you have a site which disables a users' password after a certain number of failed attempts, it is best to disable this if possible. As the scanner will attempt various logins and combinations of authentication, it’s best if the login does not become locked out.

`Password resets`: Pages containing user personalization often contain a “reset password” link or input. In order to prevent the scanner from resetting the password during an analysis, it is best to prevent this feature from being exercised. You can use a blocklist setting to ensure the scanner does not click on such a link.

`Considerations for MFA`: Veracode Dynamic Analysis is meant to be performed in an unattended state. This means that if your web application uses an MFA token, a user cannot be prompted to enter a unique code throughout the scan. One common approach to handle this situation is to disable the MFA requirement for specific test user account used by the scan engine at the time of the analysis. This allows the scanner to login/logout multiple times during the scan and not be locked out. 

> Note: There may be a possible solution to bypass some MFA in the future

`Password variables`: A further consideration for protecting as well as updating the login credentials periodically without modifying the configuration, is to use the password credentials API and variables feature.

## Crawl Script Best Practices ##
For cases where automated crawling and exploring is not sufficient, Dynamic Analysis supports crawl scripts – prerecorded sequences of actions to take in the web application that can guide the scanner to exercise parts of the application it might not exercise otherwise.

This section contains some best practice recommendations for authoring crawl scripts to improve successful execution of the scan and improve web application coverage.

### When you might need a crawl script ###
Generally, a crawl script should not be required to fully scan a web application with Dynamic Analysis. The only time that a crawl script is absolutely needed is when a web application has functionality that is only accessible with a particular set of inputs in a multiple step process. An example is a site that provides different functionality based on the user’s choice of region from a long drop-down list, or that restricts access to other functionality based on a user’s entry of data in part of the application.

You may also want to provide a crawl script as a hint to Dynamic Analysis if you find that a particular set of pages or functionality were not crawled during a scan of your site.

### Tips for successful crawl scripting ###
Remove pre-populated values
Cache and cookies: Always clear your cache and cookies before recording a crawl script. Remember, you may have encountered the application before but the Dynamic Analysis scanner will be visiting it for the first time and won’t be able to take advantage of any information saved in cache, cookies, or local storage.

`Input fields`: If any of the input fields are auto-populated by the browser (usually the username), Selenium will NOT record them in the script.  You must delete the auto-populated values before starting to record your script.

### Targeting elements ###
`Input fields`: The scanner normally fires events on an input field while filling in the field, so adding additional click, onFocus and onBlur events as part of the script is unnecessary and may cause problems. 

`Multiple methods`: If a step fails when the script executes, then try identifying targets by an alternative method.

`Elements with long waits`: Any command that targets an elements (like a click or type command) automatically has an implicit waitForElementPresent process that occurs with a 30 second timeout. However, in cases where an element may take longer than 30 seconds to load, you may need to add additional waits. We recommend using these sparingly as they may increase your scan duration or cause other issues with the scan. 

### General advice ###
`Avoid pauses`: Where possible avoid including pauses in the script. 



### References ###

[Veracode Doc Center | Dynamic Analysis](https://docs.veracode.com/r/Dynamic_Analysis)

- [Veracode Doc Center | Configure a Web Application Scan](https://docs.veracode.com/r/c_was_configure)
  - [Veracode Doc Center | URL configuration for web application scans ](https://docs.veracode.com/r/c_was_conf_url3)
  - [Veracode Doc Center | Selenium Commands Supported in Dynamic Analysis](https://docs.veracode.com/r/Selenium_Commands_Supported_in_Dynamic_Analysis)
      - [Veracode Doc Center | Selenium Script Best Practices](https://docs.veracode.com/r/About_Selenium_Script_Best_Practices)
  - [Veracode Doc Center | Use Single Sign-on For Web Application Scans](https://docs.veracode.com/r/About_Dynamic_Analysis_Single_Sign-On_Authentication_Recommendations)
  - [Veracode Doc Center | Configure Scanner Variables ](https://docs.veracode.com/r/Configure_scanner_variables)
- [Veracode Doc Center | Best practices for a Dynamic Analysis of web applications](https://docs.veracode.com/r/Best_Practices_for_a_Dynamic_Analysis_of_Web_Applications)

[Veracode Doc Center | Dynamic Analysis API Scans](https://docs.veracode.com/r/About_Veracode_API_Scanning)

- [Veracode Doc Center | About API Specification Scans](https://docs.veracode.com/r/About_API_Scanning_and_API_Specifications)
- [Veracode Doc Center | Create an API Specification Scan](https://docs.veracode.com/r/Create_an_API_Specification_Scan)
- [Veracode Doc Center | Configure and Run and API Specification scan](https://docs.veracode.com/r/Configure_and_Run_an_API_Specification_Scan)
  - [Veracode Doc Center | API Scanning Authentication Methods](https://docs.veracode.com/r/API_Scanning_Authentication_Methods)
  - [Veracode Doc Center | Create an API Specification Scan (Video)](https://docs.veracode.com/r/Video_Create_an_API_Specification_Scan)



[Veracode Community  : Dynamic Analysis topic, Dynamic Analysis group](https://community.veracode.com/s/topic/0TO2T000000bzrpWAA/veracode-dynamic-analysis?tabset-49418=2)
