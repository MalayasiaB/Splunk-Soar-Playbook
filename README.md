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
<img src="https://i.imgur.com/dWcNww5.png" height="80%" width="80%" alt="Honeypot Steps"/>
<br />
<br />
Opened Jira webage, created project, chose software development and bug tracking template:  <br/>
<img src="https://i.imgur.com/VVsfKm2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Titled project, created a key to finalize creation: <br/>
<img src="https://i.imgur.com/oVmfPJz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On my profile page, navigated to account settings:  <br/>
<img src="https://i.imgur.com/lCrrmRZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Clicked Security tab:  <br/>
<img src="https://i.imgur.com/YUywkRL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Scrolled and click on create and manage API key:  <br/>
<img src="https://i.imgur.com/HHSLQUt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Clicked create API token, copied it. Created token details appeared below :  <br/>
<img src="https://i.imgur.com/eFD7R31.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Back in Splunk SOAR, I  configured a new asset within Jira:  <br/>
<img src="https://i.imgur.com/ESWHtml.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Named it and provided a description left remaining inputs default:  <br/>
<img src="https://i.imgur.com/lMrYa1C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On the asset settings screen I added the url to my jira account and port number in use; 443, my email, and API key:  <br/>
<img src="https://i.imgur.com/xkQkibV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Clicked save, then test connectivity to ensure that Jira officially connected to Splunk SOAR:  <br/>
<img src="https://i.imgur.com/dEjHxiq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From there I installed another App, SMTP:  <br/>
<img src="https://i.imgur.com/V4NyZao.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Opened another webpage, and navigated to myaccout.google.com, In the top search bar I typed app password and clicked on the first result displayed here:  <br/>
<img src="https://i.imgur.com/kTjZU2K.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Created a name, this serves as the name for the app specific password I recieved. This password will serve as my API key:  <br/>
<img src="https://i.imgur.com/1MewIen.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Naviated back to Splunk SOAR and configured a new assest for SMTP. Gave it a name, description and tag and left remaining settings default:  <br/>
<img src="https://i.imgur.com/4M0UHZa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In sset settings, I pasted my app password, added my email as the username and input smtp.gmail.com as the Server IP/hostname:  <br/>
<img src="https://i.imgur.com/Sml7jId.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I saved this information and tested connectivity:  <br/>
<img src="https://i.imgur.com/MRq1OU1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigated to playbooks and clicked the create playbook icon:  <br/>
<img src="https://i.imgur.com/w3hZMwf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Selected input, Automation allows a playbook to automatically run based on triggers. For this project, input is selected as it will not run automatically everything will be configured and ran:  <br/>
<img src="https://i.imgur.com/rmHVmOP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To begin, I provided a variable name:  <br/>
<img src="https://i.imgur.com/t1lfzpm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I added SMTP as an action and provided the following input seen at the bottom right:  <br/>
<img src="https://i.imgur.com/ulGMrjX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Added Jira as my second action and provided the following inputs below:  <br/>
<img src="https://i.imgur.com/kf18uwI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Saved and ran playbook:  <br/>
<img src="https://i.imgur.com/ekzHkiM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Email alert that was integrated and configured:  <br/>
<img src="https://i.imgur.com/C7Dw1AL.png" height="80%" width="80%" alt="Disk Sanitization Steps"
<br />
<br />
Display of task created in Jira after successful run of playbook:  <br/>
<img src="https://i.imgur.com/ujUYWKt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
