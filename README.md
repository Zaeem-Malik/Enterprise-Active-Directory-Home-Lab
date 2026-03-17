# Enterprise Active Directory Home Lab 

## Objective 
[Brief Objective - Remove this afterwards]  

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned
[Bullet Points - Remove this afterwards]

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
[Bullet Points - Remove this afterwards]

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps

Step 1: Download Oracle VirtualBox and the extension pack (https://www.virtualbox.org/wiki/Downloads)  

Step 2: Download Windows Server 2019 (https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)

Step 3: Download Windows 10 (https://www.microsoft.com/en-us/software-download/windows10)

Tip: Note file location for all three downloads<br/> 

Step 4: Click on “New” and name the VM as you would like, I chose to name it DC for ‘domain controller’. Then for OS choose “Microsoft Windows” and for OS Version choose “Other Windows (64-bit)” as shown below. <br/>
<img src="https://i.imgur.com/qVO1rAC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 5: Click on settings to configure the VM. Make sure you are in expert (advanced) view. Depending on how much RAM your machine has you can choose the amount. I personally chose 4096 mb (4 GB), 2 processors, and 128 Mb video memory (This makes the GUI smoother). <br/>
Tip: Allocated at least 2048 MB (2 GB) for RAM
<img src="https://i.imgur.com/WuAefLk.gif" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>

Step 6: Click on storage and ‘add optical drive’, then select the Windows server 2019 iso as shown below. <br/>
<img src="https://i.imgur.com/4YbZzWZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/D7EjDCJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
