<h1>Jira Playbook using Splunk SOAR</h1>


<h2>Description</h2>
Project consists of a local instance of Splunk SOAR configured for automation and incident response testing. The environment includes Jira for ticketing and an SMTP service for email notifications, both integrated through generated API keys to allow secure communication between platforms. A custom playbook was created using the installed apps and configured to automate response actions. The playbook was executed in a test environment to verify integration and functionality.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Jira</b> 
- <b>API Keys</b>
- <b>Gmail</b>

<h2>Environments Used </h2>

- <b>Windows 11</b> (24H2)

<h2>Program walk-through:</h2>

<p align="center">
Navigated to Apps, Installed Jira: <br/>
<img src="./images/filename1.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Opened Jira webage, created project, chose software development and bug tracking template:  <br/>
<img src="./images/filename2.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Titled project, created a key to finalize creation: <br/>
<img src="./images/filename3.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
On my profile page, navigated to account settings:  <br/>
<img src="./images/filename4.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Clicked Security tab:  <br/>
<img src="./images/filename5.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Scrolled and clicked on create and manage API key:  <br/>
<img src="./images/filename6.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Clicked create API token, copied it. Created token details appeared below :  <br/>
<img src="./images/filename7.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Back in Splunk SOAR, I  configured a new asset within Jira:  <br/>
<img src="./images/filename8.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Named it and provided a description, left remaining inputs default:  <br/>
<img src="./images/filename9.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
On the asset settings screen I added the url to my jira account and port number in use; 443, my email, and API key:  <br/>
<img src="./images/filename10.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Clicked save, then test connectivity to ensure that Jira officially connected to Splunk SOAR:  <br/>
<img src="./images/filename11.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
From there I installed another App, SMTP:  <br/>
<img src="./images/filename12.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Opened another webpage, and navigated to myaccout.google.com, In the top search bar I typed app password and clicked on the first result displayed here (2-factor authentication has to be enabled for this to work):  <br/>
<img src="./images/filename13.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Created a name, this serves as the name for the app specific password I recieved. This password will serve as my API key:  <br/>
<img src="./images/filename14.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Naviated back to Splunk SOAR and configured a new assest for SMTP. Gave it a name, description and tag and left remaining settings default:  <br/>
<img src="./images/filename15.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
In settings, I pasted my app password, added my email as the username and input smtp.gmail.com as the Server IP/hostname:  <br/>
<img src="./images/filename16.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
I saved this information and tested connectivity:  <br/>
<img src="./images/filename17.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Navigated to playbooks and clicked the create playbook icon:  <br/>
<img src="./images/filename18.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Selected input, Automation allows a playbook to automatically run based on triggers. For this project, input is selected as it will not run automatically everything will be configured and ran:  <br/>
<img src="./images/filename19.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
To begin, I provided a variable name:  <br/>
<img src="./images/filename20.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
I added SMTP as an action and provided the following input seen at the bottom right:  <br/>
<img src="./images/filename21.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Added Jira as my second action and provided the following inputs below:  <br/>
<img src="./images/filename22.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Saved and ran playbook:  <br/>
<img src="./images/filename23.png" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Email alert that was integrated and configured:  <br/>
<img src="./images/filename24.png" height="80%" width="80%" alt="SOAR"
<br />
<br />
Display of task created in Jira after successful run of playbook:  <br/>
<img src="./images/filename25.png" height="80%" width="80%" alt="SOAR"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
