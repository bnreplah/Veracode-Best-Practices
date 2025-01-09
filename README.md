# Veracode Best Practices #
---

[Prevent](#prevent)    
[Detect](#detect)   
[Respond](#respond)   

## Challenges:
- [Secure Entire SDLC](https://www.veracode.com/integrate-security-into-the-sdlc-1)
- [Build Developer Security Copetency](https://www.veracode.com/build-developer-security-competency)
- [Protect the Software Supply Chain](https://www.veracode.com/secure-the-software-supply-chain)
- [Manage the Web App Attack Surface](https://www.veracode.com/manage-web-app-attack-surface-risk)
- [Secure Cloud Development](https://www.veracode.com/secure-cloud-development)

## Core Capabilities:
- Threat Insights
    - Research and analysis of the software risk landscape from dedicated industry experts with decades of experience
- On-Demand Experts
    - Global team of software security experts readily available to assist in achieving your security program objectives
- Comprehensive Scanning
    - All software security capabilities required by modern AppSec program on a single platform
- AI-assisted Remediation
    - Increase developer efficiency and increase software security with automation and AI-assisted fixes
- Analytics and Benchmarking
    - Measures software security maturity against peer organizations and report to executives and board of directors

## Benefits:
- Rapid Time to Value
    - Onboard quickly, without sacrificing the speed of development or security. Start finding and fixing flaws right away.
- Easy to Use and Integrate
    - Modern, intuitive user-experience that easily integrates with development tools, risk-tracking systems and security controls.
- Actionable Results
    - Unified reporting and analytics make governance, risk management, and compliance easy
- Unified platform
    - No need for point products. Single platform providing an end-to-end software security solution
- Effective Risk Reduction
    - Understand and measure risk, prioritize remediation guidance, and report on the results

# Prevent #
```
Security starts with prevention through education, promoting secure coding practices for secuirty and development teams
```

## Veracode Vulnerability Database ##
[About the Veracode Vulnerability Database](https://docs.veracode.com/r/About_the_Veracode_Vulnerability_Database)

The Veracode Proprietary Vulnerability Database catalogs all the open-source libraries from multiple resources, along with include syncing open-source vulnerability data from the NVD. The vulnerability database also include some OS package information. The Vulnerability Database also include entries not found in the NVD.

The Vulnerability Database can be used to assess which libraries are safe for use before including them in your code. Organizations can use the Veracode Vulnerability Database in order to assess which package they want to include in their artifact store, or which libraries to approve for use.

### Usage ###
You can use the vulnerability database in a couple of ways. You can access it from your browser, from the SCA Agent CLI, from the APIs
It can be used to look up vulnerabilities as well as look up libraries with their associated vulnerabilities as well as the next safe version of a library.

You can search between libraries and vulnerabilities

#### From the Browser ####
[Veracode Vulnerability Database](https://sca.analysiscenter.veracode.com/vulnerability-database/search#_)

Authenticated you can access the propritary data and get exposed to more data from an authenticated view


#### From the CLI ####
[Veracode SCA Agent-Based Commands](https://docs.veracode.com/r/Veracode_SCA_Agent_Commands#lookup)
[Veracode Unofficial DB Lookup Wrapper](https://github.com/bnreplah/veradblookup)


#### From the APIs ####
[SwaggerHub SCA Documentation](https://app.swaggerhub.com/apis/Veracode/veracode-sca_agent_api_specification/3.0#/registry)




## SDLC ##
[Secure Entire SDLC](https://www.veracode.com/integrate-security-into-the-sdlc-1)
```
Integrate security across the SDLC with AI and automation to find and fix software vulnerabilities
```

You want to design with security integrated into you SDLC

### Plan ###

#### Best Practices ####
- Design integrations and workflows that work with your SDLC in mind
- Define an application inventory list to easily onboard and track application scan requirements and progress
- Secure Entire SDLC by ensuring that there is some sort of security testing being conducted at every stage of the SDLC
- Review Libraries before approving the Library for use with developers in the Veracode Vulnerability Database
- If you are planning on using containers, scan the container image version for any known vulnerabilities, use the container scanning to address any configuration issues with the container before use.
- Integrate into the SDLC to make scanning seamless and to have scan results quality gate at higher levels of the SDLC
- Ensure you have reporting being generated and saved at a frequent cadence, as well and store artifacts and reports generated within your pipelines for retention of results

- Make sure the program satisfies business requirements
- Apply secure design and threat modeling as needed
- Ensure the right language is used in the development process
- Use appropriate mapping for testing purposes

### Code and Build ###

#### Best Practices ####
- Train coders in secure development
- Find and fix defects while writing code
- Ensure security of open-source components
- Reduce test time

### Test ##

#### Best Practices ###

- Use multiple testing methods for security testing
- Comprehensive performance, functional, unit, and integration testing are important

### Stage ##

#### Best Practices ###
- Progress and component tracking
- Automated release processes
- Security testing and quality checks

### Deploy and Monitor ##

#### Best Practices ###

- regularly scan the application both with static and Dynamic to see if any new attack vectors are exposed


## AppSec Best Practices ##
[Veracode Community AppSec Best Practices Guide](https://community.veracode.com/s/knowledgeitem/appsec-best-practices-MC5HU2OIHZYFALPAZCKZL4AAITLU)
[The Role of Web Application Security Best Practices in DevOps by Cody Bertram](https://www.veracode.com/blog/secure-development/top-6-devops-web-application-security-best-practices)


### Identify  ###

Identify your attack surface

- Idenitfy Admins, New Users, Teams, App Workflow, and Security Champions
- Identify the requirements and stretch goal in regards to a Remediation Plan
- Identify those who would need access to veracode
- Identify the role team structure, know what roles each team will have within.
- Identify your attack surface


### Get a Baseline ##

Know what is in your sources of risk

- Scan your applications for the first time in the platform
- Ensure that they are pacakged correctly according to the packaging and compilation guides within the documentation
- When you upload your application to a profile for the first time, whether it is a policy scan or sandbox scan


### Establish Remediation Strategy  ###

Define and assign security policies based on risk tolerance

Further establish the desired remediation stretegy. 
- How will remediation be structure, who will be in charge of the remediation efforts for every team?
- who will be responsible for approving mitigations for each team?
- How will mitigations be handled?
- Who will be approving mitigations, will it be done by the team themselves?
- Will anybody be reviewing mitigations after they have been approved to expire old mitigations? Has this timeframe been defined?

### Remediate, Mitigate, Fix ###

Triage and Address Security Findings and Trends



### Review Analytics ###

Iterate and Improve on Your Continuous and Measured Program 

Review analytics on the data and review trends around the data to see how the Remediation cycle is going.
Utilize the data from analytics to better optimize scans and workflows.
Utilize the analytics data to check on the status of applications, findings, compliance, and more


### Optimize ###

Prevent New Flaws with Education and Engagement

Use the information gathered from feedback from the teams along with reviewing the analytics data to optimize the process and pipelines.
- Further Automate your scanning process
- Automate the ticketing process to keep track of flaws
- Automate common API calls
- Automate the feedback proccess from developers
- Determine which teams need security training first
- Determine whether a company wide security training is needed
- Determine whether targetted training modules are needed



# Detect #
```
Detect flaws and vulnerabilities across the entire SDLC with comprehensive scanning
```
## SAST ##
[Veracode Getting Started with Static](https://docs.veracode.com/r/Static_Analysis_Quickstart)

### General Best Practices ###

- When you first scan into an application profile for the first time, Veracode recommends that you mannually compile and package your application with debug symbols to ensure that you have a properly package application.
- Veracode Recommends that you turn off auto-scan after prescan for the first time that you upload an application to be scanned in either a sandbox or policy scan.
- Following the prescan on that first scan, with auto-scan after prescan off, the scan will be in a state of module selection. This is will require the scan to have the modules mannualy selected. Proper module selection is crucial to an accurate scan.
- Following the initial scan, automation can now be set up, and every subsequent scan in the policy or sandbox with auto-scan on will auto select the previous module selection. It will require manual module selection if there is an error in the files or fatal error in a previously selected module. See the available upload and scan 
- If you have any problems or questions, contact your support team for assistance.
- For remediation guidance, to review false postives, and more, schedule a consultation call to talk to our Application Security Consultants



### Module Selection ###
[Veracode Community | What are Modules and how do my results change based on what I select ?](https://community.veracode.com/s/article/What-are-Modules-and-how-do-my-results-change-based-on-what-I-select)
[Veracode Docs | About Top-level Modules](https://docs.veracode.com/r/About_Top_Level_Modules)
```
A module represents a discrete component of the uploaded application that Veracode analyzes. A prescan of the application identifies top-level modules, which are the components identified that have entry points for external data. Entry points typically are modules that include first-party code. You can only select the top-level modules to scan.

```
To better understand a what makes a proper upload, it is good to [understand possible warnings and errors and their resolutions](https://docs.veracode.com/r/errors_master)


## SCA ##
The first step to decide if you should or should not use a component is to use either lookup or getLibrary commands. They will provide the details of the release and vulnerabilities for each library based on our Veracode Vulnerability Database. Please note, our private database contain premium data, and vulnerabilities not available in the NVD.


After checking if the library is safe to be used, you should clone the branch you planning to have the library added and then run the srcclr from your CLI using our –no-upload –update-advisor, which will provide the results in your CLI without creating a new project in your workspace. Here are the instructions, Install the Veracode SCA CLI Agent.


Lastly, you can add components to a [blocklist](https://docs.veracode.com/r/c_blocklist). When Veracode finds blocklisted components in applications during a scan, the scan results report a scan policy violation. You can label the policy violations as mitigated, replace or fix the vulnerable component.

Additionally, you can integrate to your IDE using [Veracode SCA Scan for VS Code](https://docs.veracode.com/r/Veracode_SCA_Scan_for_VS_Code) to scan and update which one of your libraries.


## DAST ##


### TLDR ###
Start with a prescan, quick scan , then full authenticated scan, then a crawl script if needed, then look at allowed and denied urls to strict and expand scope


### How it works ##

Veracode Dynamic Analysis interacts with the application like an attacker. It starts by performing a crawl to understand the application’s architecture, including links, text, form fills, and other page elements that a user could potentially interact with. It also picks up on attack points that are less visible to the user, such as header values, cookies, and URL parameters. The scanner then audits the objects and attributes discovered by the crawl and sends attacks – like Cross-Site Scripting and SQL Injection – to the objects/attributes to see if they have any exploitable vulnerabilities.


Today’s web applications are complex and full of features and functions for users to interact with. Likewise, a dynamic analysis crawler will not only need to interact with the application in the desired way, but will also exercise each part of the application with payloads that test for vulnerabilities. 


Veracode Dynamic Analysis scan engine is designed to test production web applications with minimal impact, and uses testing approaches that do not harm the site or accidentally delete data. The more complex a web application is, the more requests and permutations of tests will be required, which take time to complete.


This document outlines several approaches to optimizing the scan configuration in order to provide a comprehensive audit of your web application.


### Review scan coverage report ##
Unless you are keenly aware of the exact structure and functionality of your web application, the first scan should be treated as a reconnaissance analysis. Initially, a Dynamic Analysis scan should be run without many guardrails, so that it can freely explore your web application and populate the Coverage Report with as much detail as possible. 


Once you have completed the initial scan, you can begin to review the Coverage Report. The Coverage Report provides a wealth of information with regards to what the scan engine’s experience was during an automated crawl of your web application. Within the Scan Coverage report, you can begin to see patterns of behavior and take steps to help optimize the scan configuration. 


#### Eliminating Redundant Content ###
One of the major outcomes of reviewing the Coverage Report is to further enhance the built-in redundancy checks of the scanning engine to account for the uniqueness of your web application. Veracode Dynamic Analysis has built-in redundancy checks and will recognize similar content as it traverses throughout the web application. However, some we applications create content in such ways where only a human can determine that the same code functionality is driving the presentation layer.


#### Inform the scan engine of similar content: ###
As patterns emerge during review of the Coverage Report, you can note these down and use the Allowlist and Blocklist functionality to enter in  

use the allowlist and blocklist feature to remove duplicate pages/content


#### Links to tracking sites and ad servers: ###
Many of today’s web applications include links to elements used to track user behavior and provide a wealth of information to marketing and analytics teams. However, these can also create a lot of noise for automated crawlers which will “see” all these links and still perform a GET request while they initially load each page for further inspection. While in almost all cases there is no need to do take any action on these types of links, in some cases there can be so many of these trackers that can in fact contribute to the time it takes to scan a web application. If you notice an over abundance of links to various external trackers and even ad serving URLs, take note of the most common domains


In general the amount of 3rd party traffic is not related to time spent scanning. The browser itself and customer apps have 3rd party content and it is requested as part of the scanning process. More often in cases like this, the real problem is related to automated content generation i.e. we generate content on the site in a way that fools the dupe check so we keep seeing everything as "new". At the moment, we unfortunately don't expose any of the controls that can be used to combat this, but there are some settings an internal operator can tweak to adjust this. Most directly, there is a alternate detection scheme from default that uses the URL in the browser window to determine uniqueness. This sometimes is a better fit and can help scans go faster. Also, with the default setting there is a similarity threshold that is set to .95 by default lowering this to .90 or .85 often helps the dedupe algorithm drop content more reliably. This setting is truly never one-size-fits-all anyway, so some adjustment to it is often beneficial.

I do hope someday we can expose these settings, along with details on how they work, so an advanced user could make these adjustments themselves, but for now it would probably need a support ticket to investigate further or make adjustments.

#### Links to disruptive areas of the web application: ###
delete/reset, delete user, can sometimes be available via a simple link to high-priveleged users. Ensure the test account used for scanning does not have this type of access or specifically block the functionality.

With API specification scans, you can control which endpoints will be auditted. You should review and remove any endpoints that may cause some destructive behavior.

### Expand the scope of the scan ##
While we focused on areas where the scan engine explored too much of the site and increased scan time, there are instances where it may have missed areas of the web application due to too narrow of a scope defined.

#### Subdomains ###
Take, for example, a site that includes subdomains… if they are in scope, add them to the allowlist so that the crawler can transition from one subdomain to another when it encounters a link to that content. This is particularly useful if you wish for a single report encompassing a full web application.

#### Directories and Subdirectories ###
Take note of the “Directory, Directory and subdirectory” scan settings. In some instances, the content you may wish to scan is organized by directory on the same root domain. 


### Improve Network connectivity ##
In some cases, the responsiveness of the target web application can impact the duration of the overall scan. Keeping the following considerations in mind can help with a faster scan time. 

First, schedule the scan during low load-times so the site can respond quicker to the many requests Dynamic Analysis will be sending. Remember that unlike a human user, the Dynamic Analysis engine will send multiple requests to the same resource as it performs various tests.

Second, if using Veracode Internal Scan Management (ISM), place the ISM as close to target application as is possible. For example, install ISM in same datacenter or network segment as target app to decrease the number of hops required to reach the target application.

### Authentication Best Practices ##
Veracode Dynamic Analysis is often used to test applications which require authentication. Many authentication methods are support and well documented in the Veracode Help Center. To help eliminate scan failures or scans with little or no coverage when scanning authenticated sites, there are a few best practices to keep in mind.

`Test credentials`: do not use personal real credentials. The crawler will login with these and use them to perform testing. It is best to use test credentials created specifically for scanning purposes.

`Password lock out`: If you have a site which disables a users' password after a certain number of failed attempts, it is best to disable this if possible. As the scanner will attempt various logins and combinations of authentication, it’s best if the login does not become locked out.

`Password resets`: Pages containing user personalization often contain a “reset password” link or input. In order to prevent the scanner from resetting the password during an analysis, it is best to prevent this feature from being exercised. You can use a blocklist setting to ensure the scanner does not click on such a link.

`Considerations for MFA`: Veracode Dynamic Analysis is meant to be performed in an unattended state. This means that if your web application uses an MFA token, a user cannot be prompted to enter a unique code throughout the scan. One common approach to handle this situation is to disable the MFA requirement for specific test user account used by the scan engine at the time of the analysis. This allows the scanner to login/logout multiple times during the scan and not be locked out. 

> Note: There may be a possible solution to bypass some MFA in the future

`Password variables`: A further consideration for protecting as well as updating the login credentials periodically without modifying the configuration, is to use the password credentials API and variables feature.

### Crawl Script Best Practices ##
For cases where automated crawling and exploring is not sufficient, Dynamic Analysis supports crawl scripts – prerecorded sequences of actions to take in the web application that can guide the scanner to exercise parts of the application it might not exercise otherwise.

This section contains some best practice recommendations for authoring crawl scripts to improve successful execution of the scan and improve web application coverage.

#### When you might need a crawl script ###
Generally, a crawl script should not be required to fully scan a web application with Dynamic Analysis. The only time that a crawl script is absolutely needed is when a web application has functionality that is only accessible with a particular set of inputs in a multiple step process. An example is a site that provides different functionality based on the user’s choice of region from a long drop-down list, or that restricts access to other functionality based on a user’s entry of data in part of the application. This is the use case for sites with more complicated business logic.

You may also want to provide a crawl script as a hint to Dynamic Analysis if you find that a particular set of pages or functionality were not crawled during a scan of your site.

#### Tips for successful crawl scripting ###
Remove pre-populated values
Cache and cookies: Always clear your cache and cookies before recording a crawl script. Remember, you may have encountered the application before but the Dynamic Analysis scanner will be visiting it for the first time and won’t be able to take advantage of any information saved in cache, cookies, or local storage.

`Input fields`: If any of the input fields are auto-populated by the browser (usually the username), Selenium will NOT record them in the script.  You must delete the auto-populated values before starting to record your script.

#### Targeting elements ###
`Input fields`: The scanner normally fires events on an input field while filling in the field, so adding additional click, onFocus and onBlur events as part of the script is unnecessary and may cause problems. 

`Multiple methods`: If a step fails when the script executes, then try identifying targets by an alternative method.

`Elements with long waits`: Any command that targets an elements (like a click or type command) automatically has an implicit waitForElementPresent process that occurs with a 30 second timeout. However, in cases where an element may take longer than 30 seconds to load, you may need to add additional waits. We recommend using these sparingly as they may increase your scan duration or cause other issues with the scan. If you need to use any waits we recommend that you use implicit wait commands such as `waitForElementPresent` or `waitForTextPresent` instead of explicit pauses or waits

#### General advice ###
`Avoid pauses`: Where possible avoid including pauses in the script. 



## Integrations ##
[Integrate Security Into the SDLC](https://www.veracode.com/integrate-security-into-the-sdlc-1)

### Quick Links ###
- [Pipeline Scanner Documentation](https://docs.veracode.com/r/Pipeline_Scan)
- [Software Composition Analysis Documentation](https://docs.veracode.com/r/c_integrated_benefits)
- [Static Analysis Documentation](https://docs.veracode.com/r/c_static_overview)


#### Best Practice Guides ###

[Veracode Community AppSec Best Practices Guide](https://community.veracode.com/s/knowledgeitem/appsec-best-practices-MC5HU2OIHZYFALPAZCKZL4AAITLU)

#### Veracode Community Integration Scripts ##
[Veracode Community Open Source Projects](https://github.com/veracode/Veracode-Community-Projects)
[GitHub Example: Verademo](https://github.com/veracode/Verademo)




### Pipeline Scans CI Best Practices ##
When performing static analysis testing in a Continuous Integration (CI) pipeline, the goal should be to quickly identify potential software vulnerabilities so that newly introduced security defects are not passed downstream into production. There are many workflows of issue management that can be applied on security findings that are not caught and fixed right away but introducing them into a pipeline slows the team’s flow and constrains value delivery (including delivery of security fixes).

Wherever possible, Pipeline Scan should be used in CI instead of Policy Scan or Sandbox Scan. That said, there are a few reasons you might not be able to apply Pipeline Scan to your application:

Application development language. Veracode is rapidly adding languages to Pipeline Scan, but if your team develops using one of the languages not yet supported, you may need to use a Policy or Sandbox Scan instead.

Application size. Pipeline Scan supports testing application artifacts up to 100 MB in size. This is sufficient for most modern application development including microservices, but may not work for larger, monolithic code bases. For these applications, you may need to use a Policy or Sandbox Scan instead.

### Application Profile And SandBox Best Practices ##

#### Use a consistent sandbox structure to scale AppSec Practices ###
Defining a consistent sandbox structure, rather than forcing each team to figure out their own ways to manage their sandboxes, allows you to onboard each new development team more quickly, shortening the time to getting actual results. Based on the experience of thousands of development teams, we recommend the usage of sandbox for Release Candidates and different stages of development
- Trigger scans in the Release Candidate sandbox when code is merged into the main brach
- Promote only from this sandbox
- It is also recommended to only approve mitigations from this sandbox ( the final release candidate sandbox)
- If necessary, use one or more additional sandboxes to test the application in earlier stages of development, e.g. when merging a feature branch to main. This is mostly for applications that cannot yet use Pipeline Scan to do early stage static testing, due to language support or application size.

#### General recomendations for shifting left ###

- Set up the application profile(s) for your applications based on the specific use cases listed below.
- Use IDE Scan while coding to get instant feedback.
- Use Pipeline Scan in the Continuous Integration pipeline to scan each application, tracking metadata for each scan such as the platform application ID to permit reporting in Analytics.
- Use the Release Candidate development sandbox to prepare mitigations, if desired, before pushing the application into production. (Automate this process in the late stage of your pipeline, or on a daily or weekly schedule.)
- Do a policy scan or promote a Sandbox Scan from the Release Candidate sandbox when the application goes into production, so you have a record of how the application has done against your policy
- when you start rolling out blocking, or gateing, start with just gating on net new flaws, and then start to work back from there not to overwhelm. 

#### Application profiles for Microservices applications ###

- Implement each microservice as its own App Profile
- Sandbox usage is restricted to feature branch / variations of that microservice (e.g. limited)
- Aggregate reporting: use Analytics
- Mitigations in shared code: use Mitigation Copier or similar script

#### Multiple Branches or Application Versions in Production ###

- Use separate application profiles
- Mitigations in shared code: use Mitigation Copier or similar script

### When Migrating from Sandbox Scans to Pipeline Scan ##

#### Large Monolithic Applications ###
- Break the application up into smaller components, submitting each as its own scan in a unique application profile
- For reporting, use custom fields and Analytics

#### Checking for pipeline scan compatibility ###
Ensure the application is compatible with Pipeline scans before getting started with the migration from Policy to Pipeline.

Pipeline scan requirements: https://help.veracode.com/r/c_pipeline_scan_packaging

#### Managing the Pipeline Scan CLI tool ###
There are multiple ways to manage availability of the Pipeline Scan tool in your pipeline. One common pattern is to download the tool before each invocation of the pipeline, using commands similiar to the YAML below:

```yaml
script:

  - curl -O https://downloads.veracode.com/securityscan/pipeline-scan-LATEST.zip 

  - unzip pipeline-scan-LATEST.zip pipeline-scan.jar
```
 
This script ensures that the latest version of the Pipeline Scan tool is always used, at the cost of downloading the small JAR file on each invocation of the pipeline. Alternatives include caching the JAR file on the CI server and refreshing it once a day. Depending on your CI server, you may find it more convenient to use the Pipeline Scan tool in a Docker image, such as the one published by Veracode.

#### Checking credentials expiration ###
You can use the veracode lightweight healthcheck API and other APIs to validate and ensure the credentials are valid.
[Get API credentials expiration with the REST API](https://docs.veracode.com/r/c_identity_creds_expire)


#### Application with Multiple Modules ###

Some Veracode applications may have multiple modules — separate DLLs and executables, or applications containing multiple languages. If possible, within the size constraints of Pipeline Scan, it is best to submit these as a ZIP file, or if necessary, you can submit each module as a separate Pipeline Scan call. The script linked above will produce a sample command line for each module of a multiple module application. Please note that there is a limit on the number of Pipeline Scan calls that can be made at a time (currently limited to six calls a minute), so you may want to add some wait statements before submitting additional modules.


#### Stopping the pipeline based on policy ###
You can use a policy defined in the Veracode Platform or with the Policy REST API to evaluate the results of a Pipeline Scan.

A Pipeline Scan can directly evaluate the results against one of the standard Veracode policies, including the Veracode recommended policies. For a [custom policy](https://docs.veracode.com/r/Using_Policies_with_the_Pipeline_Scan), you must first obtain the policy definition from the Veracode Platform. Get the policy by calling `pipeline-scan.jar` with the `--request_policy` parameter.

Because a Pipeline Scan performs a static scan and is not aware of the full history of findings, it supports only these policy rule types:

- Findings with CWE ID
- Findings in CWE Category
- Findings by Severity

When using a Veracode policy, a Pipeline Scan does not consider grace periods, required scan frequency, or evaluation timeframes.

#### Managing security debt with baseline files ###
It is common for existing applications to have security debt—known security issues that have been granted a temporary exception from policy via a grace period or mitigation. You can keep the Pipeline Scan from halting the pipeline on this security debt while still stopping on newly discovered issues by placing the findings in a baseline file. 

The most straightforward way to create a baseline file is to copy the JSON output of the Pipeline Scan tool (created with the –jf parameter) to a new file and passing it as input with the –bf parameter. We recommend managing the baseline file for an application in the source repository along with other configuration files so that the file can be monitored for changes.

#### Handling Mitigations ###

A common question about the Pipeline Scan is how to avoid halting the pipeline on flaws that have been mitigated. The best practice is to add these flaws to the baseline file (supplied to the Pipeline Scan command line with the –bf parameter) so that these flaws will not cause the pipeline to be terminated.


#### Reporting on Pipeline Scan Activity ###

Reports on Pipeline Scan activity are provided through Veracode Analytics. You can view activity in the built in Veracode Dashboards by selecting the Greenlight Usage dashboard and filtering by Scan Type = pipeline. You can make the reporting richer by including the [optional parameters](https://docs.veracode.com/r/r_pipeline_scan_commands) for application ID, project name, project URL, and development stage; these data fields are available in the [IDE and Pipeline Scans Data Explore](https://docs.veracode.com/r/c_using_explore) so that you can create your own looks and dashboards with this data.



Some considerations:
- Business criticality: How important is this application to the business and how does this affect security risk acceptance? 
- Deployment Frequency: How often does the organization deploy code to production or release it to end-users? 
- Lead time for changes: How long does it take to go from code committed to code successfully running in production?
- Deployment: Is this application contained internally or is it externally facing in production?
- Architecture: How is the application designed?


# Respond #
```
AI-assisted remediation generates fixes developers can accept and apply in the IDE, saving time and maintaining development velocity
```

With Veracode Fix, you can get an additional layer of remediation guidance through curated recomendations. After a fix is applied it should be checked, recompiled, retested and rescanned. Fixes shouldn't be made blindly and should have a developer or a member of security review the fix before applying it or commiting it to the main codebase.

Remediation Guidance Texts are available for certain CWEs. In the details of each flaw is also the reference to the CWE record on multiple public references. This allows the developer to gain more insight into the context of the flaw and the potential impact of the flaw. There is also targetted eLearning modules to help aid by providing education modules around the flaw and how to prevent the flaw. 

Looking at some of the most prevalant CWEs and Categories in an organization can be a good start to design a targeted curriculum to help reduce the ongoing technical debt. 

## Veracode Fix ##
[Veracode Fix best practices under construction] Coming Soon



# Resources #


## Veracode Docs:

- [Veracode Doc Center](https://docs.veracode.com/)
- ~~[Veracode Docs | All Links](https://docs.veracode.com/r/all_HC)~~
- ~~[Veracode Docs | All Videos](https://docs.veracode.com/r/all_videos_HC)~~
- [Veracode Docs | Getting Started with the Platform](https://docs.veracode.com/r/start)
- [Veracode Docs | Getting Started with Static](https://docs.veracode.com/r/Static_Analysis_Quickstart)
- [Veracode Docs | Getting Started with Dynamic](https://docs.veracode.com/r/Dynamic_Analysis)
- [Veracode Docs | Getting Started with Software Composition Analysis](https://docs.veracode.com/r/c_integrated_benefits)
- [Veracode Docs | Getting Started with the APIs](https://docs.veracode.com/r/REST_APIs_Quickstart)
- [Veracode Docs | Getting Started with Security Labs](https://docs.veracode.com/r/Security_Labs_Quickstart)

### SAST:

- [Veracode Docs | Select Modules to Scan for Veracode Static Analysis](https://docs.veracode.com/r/c_request_modules_scan)
- [Veracode Community | What are Modules and how do my results change based on what I select ?](https://community.veracode.com/s/article/What-are-Modules-and-how-do-my-results-change-based-on-what-I-select)
- [Veracode Docs |  Packaging Cheat Sheet](https://docs.veracode.com/cheatsheet/?utm_source=docs&utm_medium=article&utm_campaign=packaging-guidance)

### DAST:

- [Veracode Docs | DAST Best Practices for Web Applications](https://docs.veracode.com/r/Best_Practices_for_a_Dynamic_Analysis_of_Web_Applications)
- [Veracode Docs | DAST Selenium Best Practices](https://docs.veracode.com/r/About_Selenium_Script_Best_Practices)
- [Veracode Docs | DAST ISM Endpoint Best Practices](https://docs.veracode.com/r/c_endpoint_best_practices)

### SCA: 

- [Veracode Docs | SCA Best Practices for Automated CICD](https://docs.veracode.com/r/Veracode_SCA_Best_Practices_for_Automated_CICD)
- [Veracode Docs | SCA Best Practices for Reviewing Compliance for Periodic Releases](https://docs.veracode.com/r/Veracode_SCA_Best_Practices_for_Reviewing_Compliance_for_Periodic_Releases)

### Integrations:

- [Veracode Docs | Veracode Integrations](https://docs.veracode.com/r/Veracode_Integrations)
- [Veracode Community | Veracode Integration Hub](https://community.veracode.com/s/integrations)
- [Veracode Docs | About Veracode API Best Practices](https://docs.veracode.com/r/About_Veracode_API_Best_Practices)
- [Veracode Docs | Veracode Findings Best Practices](https://docs.veracode.com/r/review_bestpractices)
- [Veracode Docs | Veracode Greenlight Best Practices](https://docs.veracode.com/r/c_best_practices)
- [Veracode Docker Images](https://hub.docker.com/u/veracode)

## Veracode Blog:

- [Veracode Blog | PM Perspective on Best Practices Scaling AppSec Program](https://www.veracode.com/blog/managing-appsec/veracode-program-managers-perspective-best-practices-scaling-appsec-program)
- [Veracode Blog | Top 6 DevOps Web Application Security Best Practices](https://www.veracode.com/blog/secure-development/top-6-devops-web-application-security-best-practices)
- [Veracode | AppSec Best Practices ](https://community.veracode.com/s/knowledgeitem/appsec-best-practices-MC5HU2OIHZYFALPAZCKZL4AAITLU)
- [Veracode Blog | How to Engage Developers to Build a Successful Application Security Program](https://www.veracode.com/blog/managing-appsec/how-engage-developers-build-successful-application-security-program)
- [Veracode Blog | Securing APIs: Practical Steps to Protecting Your Software](https://www.veracode.com/blog/managing-appsec/securing-apis-practical-steps-protecting-your-software)
- [Veracode Blog | Secrets Management Best Practices: Secure Cloud-native Development Series](https://www.veracode.com/blog/research/secrets-management-best-practices-secure-cloud-native-development-series)
- [Veracode Blog | Application Security Best Practices](https://www.veracode.com/blog/customer-news/application-security-best-practices)
- [Veracode Blog | Best Practices and Practical Steps to Guide Your AppSec Journey](https://www.veracode.com/blog/intro-appsec/best-practices-and-practical-steps-guide-your-appsec-journey)
- [Veracode Blog | Developer Training Checklist: 5 Best Practices](https://www.veracode.com/blog/intro-appsec/developer-training-checklist-5-best-practices)
- [Veracode Blog | 4 Categories of Container Security Vulnerabilities (& Best Practices to Reduce Risk)](https://www.veracode.com/blog/secure-development/4-categories-container-security-vulnerabilities-best-practices-reduce-risk)
- [Veracode Blog | Getting Started With AppSec: 4 Best Practices](https://www.veracode.com/blog/managing-appsec/getting-started-appsec-4-best-practices)
- [Veracode Blog | Best Practices for Complying with Emerging Application Security Regulations](https://www.veracode.com/blog/managing-appsec/best-practices-complying-emerging-application-security-regulations)
- [Veracode Blog | Best Practices for the Adoption of Open Source Software](https://www.veracode.com/blog/managing-appsec/best-practices-adoption-open-source-software)
- [Veracode Blog | A Veracode Program Manager’s Perspective: Best Practices for Scaling an AppSec Program](https://www.veracode.com/blog/managing-appsec/veracode-program-managers-perspective-best-practices-scaling-appsec-program)
- [Veracode Blog | 3 Best Practices for Perfect Security: A Story](https://www.veracode.com/blog/2015/10/3-easy-steps-making-perfect-security-possible)
- [Veracode Blog | SDLC Best Practices: 5 Ways to Bridge the Application Security Gap](https://www.veracode.com/blog/2015/09/sdlc-best-practices-5-ways-bridge-application-security-gap-sw)
- [Veracode Blog | Vendor Management: 5 Best Practices for Secure Applications](https://www.veracode.com/blog/2015/05/vendor-management-5-best-practices-secure-applications-sw)
- [Veracode Blog | Mobile App Security: Threats and Best Practices](https://www.veracode.com/blog/2015/05/mobile-app-security-threats-and-best-practices-sw)
- [Veracode Blog | 5 Best Practices in Data Breach Incident Response](https://www.veracode.com/blog/2014/08/5-best-practices-in-data-breach-incident-response)
- [Veracode Blog | PCI Compliance & Secure Coding: Implementing Best Practices from the Beginning](https://www.veracode.com/blog/2014/07/pci-compliance-secure-coding-implementing-best-practices-from-the-beginning)
- [Veracode Blog | Third Party Application Analysis: Best Practices and Lessons Learned](https://www.veracode.com/blog/2012/09/third-party-application-analysis-best-practices-and-lessons-learned)
- [Veracode Blog | What is Data Integrity? Learn How to Ensure Database Data Integrity via Checks, Tests, & Best Practices](https://www.veracode.com/blog/2012/05/what-is-data-integrity)


## Veracode Community:

- [Veracode Community | How to use Veracode](https://community.veracode.com/s/how-to-use-veracode)
- [Veracode Community | Onboarding Quick Start](https://community.veracode.com/s/onboarding)
- [Veracode Community | Veracode for Developers](https://community.veracode.com/s/knowledgeitem/veracode-for-developers-MCCEADXECDKNDKLFRH4ZSLHYWUZ4)
- [Veracode Community | Beginner's Guide to Veracode Analytics ](https://community.veracode.com/s/knowledgeitem/beginner-s-guide-to-veracode-analytics-start-with-the-right-questions-MC754EKVTR7VGE3AY2JJ6T2FMKV4)
- [Veracode Community | Knowledge Base](https://www.veracode.com/security)
- [Veracode Community | Policy 101](https://community.veracode.com/s/knowledgeitem/tip-3-policy-101-MCYSBKFUDSAVEXJCU2ME6HXSCFAQ)
- [Veracode Community | Best Practice Forums](https://community.veracode.com/s/topic/0TO2T000000cwAOWAY/best-practices)
- [Veracode Community | Managing AppSec Article](https://community.veracode.com/s/topic/0TO2T000000bzqGWAQ/managing-appsec?tabset-49418=2)
- [Veracode Community | 6 Main User Roles You Should Know When Beginning to Assign Users ](https://community.veracode.com/s/article/Six-Main-User-Roles-You-Should-Know-When-Beginning-to-Assign-Users)

## White Papers and HandBooks:
- [All Veracode White Papers](https://www.veracode.com/resources?resource_type_target_id%5B3261%5D=3261)
- [Your Guide to Application Security Solutions: Whitepaper](https://info.veracode.com/whitepaper-your-guide-to-application-security-solutions.html)
- [Veracode Static Analysis WhitePaper](https://www.veracode.com/sites/default/files/pdf/resources/whitepapers/veracode-static-analysis-veracode-whitepaper.pdf)
- [The DevSecOps Playbook: Practical Steps for Producing Secure Software](https://info.veracode.com/devsecops-playbook.html)
- [Veracode Secure Coding Handbook](https://info.veracode.com/secure-coding-handbook.html)
- [Five Principles for Securing DevOps WhitePaper](https://info.veracode.com/whitepaper-five-principles-for-securing-devops.html)
