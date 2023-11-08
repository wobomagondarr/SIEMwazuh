<h1>Enhancing Security Operations with Wazuh SIEM & XDR</h1>

<h2>Introduction</h2>
Wazuh is a free and open-source Security Information and Event Management tool. This tool is powerful as it unifies XDR and SIEM protection. It offers:

- Detecting and responding to unauthorized alterations made to essential files and configurations.
- Identifying and responding to unauthorized access attempts and malicious activities occurring throughout your network.
- Centralizing and analyzing logs from diverse sources to acquire insights into system behaviors.
- Promptly recognizing and mitigating security incidents to minimize their impact.
- Actively seeking concealed threats and vulnerabilities within your environment.
- Monitoring user conduct to spot unusual or suspicious activities.
- Identifying and prioritizing vulnerabilities for the purpose of patching and remediation.
- Monitoring for insider threats and unauthorized access to data.
- Supervising and safeguarding critical applications from potential attacks and vulnerabilities.

Taking a glimpse on the general monitoring dashboard, it has a multitude of modules available for us to monitor set in 4 categories:

- **SECURITY INFORMATION MANAGEMENT**
- **THREAT DETECTION AND RESPONSE**
- **AUDITING AND POLICY MONITORING**
- **REGULATORY COMPLIANCE**
<img src="https://i.imgur.com/3UYMpr8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h2>Setup Process</h2>
I deployed Wazuh on Ubuntu using a Linode cloud Virtual Machine on: https://www.linode.com/
<img src="https://i.imgur.com/U4tnv6Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Once the linode is running we can try and connect to it with the SSH Access command on the machine you wish to set the agent on.
<img src="https://i.imgur.com/hpP5Ivs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Using Windows PowerShell, we paste the copied command
<img src="https://i.imgur.com/3NfMgdW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
After the installation has run for a few minute we type :

ls -al

the .deployment-secrets.txt file will contain our different logins and passwords.

Using the command “cat .deployment-secrets.txt” we open the file and see the first admin login that we will use in order to connect to our Wazuh dashboard

<img src="https://i.imgur.com/JSbNMkA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

We can grab the Reverse DNS address and paste in the the browser to see the login page
<img src="https://i.imgur.com/J3clGQP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

We then will be prompted with the login page
<img src="https://i.imgur.com/9bhxvt5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/3UYMpr8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
