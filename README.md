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
<img src="https://i.imgur.com/3UYMpr8.png" height="80%" width="80%"/>
<br />

<h2>Setup Process</h2>
I deployed Wazuh on Ubuntu using a Linode cloud Virtual Machine on: https://www.linode.com/
<img src="https://i.imgur.com/U4tnv6Z.png" height="80%" width="80%"/>
Once the linode is running we can try and connect to it with the SSH Access command on the machine you wish to set the agent on.
<img src="https://i.imgur.com/hpP5Ivs.png" height="80%" width="80%"/>
Using Windows PowerShell, we paste the copied command
<img src="https://i.imgur.com/3NfMgdW.png" height="80%" width="80%"/>
After the installation has run for a few minute we type :

ls -al

the .deployment-secrets.txt file will contain our different logins and passwords.

Using the command “cat .deployment-secrets.txt” we open the file and see the first admin login that we will use in order to connect to our Wazuh dashboard

<img src="https://i.imgur.com/JSbNMkA.png" height="80%" width="80%"/>

We can grab the Reverse DNS address and paste in the the browser to see the login page
<img src="https://i.imgur.com/J3clGQP.png" height="80%" width="80%"/>

We then will be prompted with the login page
<img src="https://i.imgur.com/9bhxvt5.png" height="80%" width="80%"/>

<h2>Dashboard utilities </h2>

Once inside we need to add an agent which is the machine we wish to monitor, in this case we will add Windows.

<img src="https://i.imgur.com/nvdkQHg.png" height="80%" width="80%">

This will prompt you a command to use in PowerShell in order to activate the agent

<img src="https://i.imgur.com/reK4cKy.png" height="80%" width="80%">

Once the command has been pasted and loaded, we type “NET START WazuhSvc” in order to start the service and we can see that it works

<img src="https://i.imgur.com/9xfVVVH.png" height="80%" width="80%">

In the Wazuh dashboard you can see the agent has been activated and now monitored

<img src="https://i.imgur.com/skMcJZi.png" height="80%" width="80%"/>

We can see the MITRE attack framework and it will show how our machine is vulnerable to certain tactics and how it’s being actively attacked. Another thing we certainly can see is the different compliances standards(NIST, HIPAA, GDRP, PCI, GPG) and how we stand on those.

<img src="https://i.imgur.com/8HHLK0D.png" height="80%" width="80%"/>

Another important section is the Security Configuration Assessment
<img src="https://i.imgur.com/MiH5OMC.png" height="80%" width="80%"/>

If we click on the failed results it will tell us the rationales behind them and what to to do remedy the configuration and in the relevant cases it will even tell us what MITRE attacks can be used against having such misconfiguration. 

<img src="https://i.imgur.com/9xKE5eQ.png" height="80%" width="80%"/>

With active response we can set rules in order to adjust anything to your liking

<img src="https://i.imgur.com/DNxLpeq.png" height="80%" width="80%"/>

Not only that but in our case we setup real time alerts on slack, with adjusted rules in place such as if someone tries to brute force our SSH we will receive an alert right away with the information

<img src="https://i.imgur.com/Cyl448b.png" height="80%" width="80%"/>

Due to high occurrences the 2 rules we set to protect against with a fire-wall drop timeout are:

- Rule id 5710: Attempt to log in to a non-existent user
- Rule id 5763: SSHD brute force trying to get access to the system

<img src="https://i.imgur.com/lCa6NtU.png" height="80%" width="80%"/>

The section on Vulnerabilities will tell you in real time what application are vulnerable to know or common CVEs which is a great learning opportunity while figuring out how to fix them and understanding the issues.

<img src="https://i.imgur.com/LWgyVJl.png" height="80%" width="80%"/>

The 2 critical CVEs in our case was an outdated version of Python which was fixed right away. 

<img src="https://i.imgur.com/KULrifz.png" height="80%" width="80%"/>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
