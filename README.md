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
<img src="https://github.com/user-attachments/assets/a3f0de8b-30c7-474a-8245-6ffbb1c14446" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Opened Jira webage, created project, chose software development and bug tracking template:  <br/>
<img src="https://github.com/user-attachments/assets/34c7f1db-fb30-4f72-af5e-05ef93f0a98d" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Titled project, created a key to finalize creation: <br/>
<img src="https://github.com/user-attachments/assets/e0ab1716-5b5d-4cd1-b102-b05abff8c53a" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
On my profile page, navigated to account settings:  <br/>
<img src="https://github.com/user-attachments/assets/0cf6d0e3-2d81-416d-8dc1-67581d88bda1" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Clicked Security tab:  <br/>
<img src="https://github.com/user-attachments/assets/2c5af7c7-1beb-404f-ab2d-213e68e9d281" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Scrolled and clicked on create and manage API key:  <br/>
<img src="https://github.com/user-attachments/assets/3a2aa280-6666-49c0-a29c-8508772c219d" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Clicked create API token, copied it. Created token details appeared below :  <br/>
<img src="https://github.com/user-attachments/assets/8714e99a-faf5-490a-860a-4a4fdd8948e7" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Back in Splunk SOAR, I  configured a new asset within Jira:  <br/>
<img src="https://github.com/user-attachments/assets/5bea8329-5231-47b6-9d05-72567e79d193" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Named it and provided a description, left remaining inputs default:  <br/>
<img src="https://github.com/user-attachments/assets/7ca46f57-8112-4a79-9927-10a8dccc2a8f" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
On the asset settings screen I added the url to my jira account and port number in use; 443, my email, and API key:  <br/>
<img src="https://github.com/user-attachments/assets/b122e8d7-b659-42ed-a848-dadec2d27f74" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Clicked save, then test connectivity to ensure that Jira officially connected to Splunk SOAR:  <br/>
<img src="https://github.com/user-attachments/assets/0dcc1d82-765e-436d-824c-710eb938125f" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
From there I installed another App, SMTP:  <br/>
<img src="https://github.com/user-attachments/assets/d3c1df02-c783-48b0-9466-f059c6b87297" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Opened another webpage, and navigated to myaccout.google.com, In the top search bar I typed app password and clicked on the first result displayed here (2-factor authentication has to be enabled for this to work):  <br/>
<img src="https://github.com/user-attachments/assets/78bf91a7-5bab-4452-ba3a-e9167a2efa73" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Created a name, this serves as the name for the app specific password I recieved. This password will serve as my API key:  <br/>
<img src="https://github.com/user-attachments/assets/242a8722-39a4-46d9-8e50-a7980627157c" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Naviated back to Splunk SOAR and configured a new assest for SMTP. Gave it a name, description and tag and left remaining settings default:  <br/>
<img src="https://github.com/user-attachments/assets/1eb98c55-56df-4c29-b7e9-8aaf64b35cc3" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
In settings, I pasted my app password, added my email as the username and input smtp.gmail.com as the Server IP/hostname:  <br/>
<img src="https://github.com/user-attachments/assets/5c511cae-51c0-4231-a2f1-8a1a29113923" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
I saved this information and tested connectivity:  <br/>
<img src="https://github.com/user-attachments/assets/fd849bd0-3419-4a81-b353-bba5593a8ffc" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Navigated to playbooks and clicked the create playbook icon:  <br/>
<img src="https://github.com/user-attachments/assets/df67ee5c-d126-4458-83b8-0baaf1207d32" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Selected input, Automation allows a playbook to automatically run based on triggers. For this project, input is selected as it will not run automatically everything will be configured and ran:  <br/>
<img src="https://github.com/user-attachments/assets/ee5d5ae0-1599-4ba9-8a45-733510d7fa35" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
To begin, I provided a variable name:  <br/>
<img src="https://github.com/user-attachments/assets/477ca54a-115f-43ff-b042-7b4fe8eff2dd" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
I added SMTP as an action and provided the following input seen at the bottom right:  <br/>
<img src="https://github.com/user-attachments/assets/740bfce6-3e4f-4344-b253-5e105ff9ce57" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Added Jira as my second action and provided the following inputs below:  <br/>
<img src="https://github.com/user-attachments/assets/df37c5b7-603c-4172-b08e-417d15377da7" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Saved and ran playbook:  <br/>
<img src="https://github.com/user-attachments/assets/75716a37-bef8-49ac-bb88-a06b3191aa37" height="80%" width="80%" alt="SOAR"/>
<br />
<br />
Email alert that was integrated and configured:  <br/>
<img src="https://github.com/user-attachments/assets/c26e3cd6-1c33-4f6f-b765-6a5c9647bdff" height="80%" width="80%" alt="SOAR"
<br />
<br />
Display of task created in Jira after successful run of playbook:  <br/>
<img src="https://github.com/user-attachments/assets/370153f4-f603-4c0e-b0cb-2c48d2d04b88" height="80%" width="80%" alt="SOAR"/>
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
