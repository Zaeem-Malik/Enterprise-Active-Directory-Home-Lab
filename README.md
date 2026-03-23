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
<img src="https://i.imgur.com/qVO1rAC.png" height="80%" width="80%" alt="Creating VM"/>
<br />
<br />

Step 5: Click on settings to configure the VM. Make sure you are in expert (advanced) view. Depending on how much RAM your machine has you can choose the amount. I personally chose 4096 mb (4 GB), 2 processors, and 128 Mb video memory (This makes the GUI smoother). <br/>
Tip: Allocated at least 2048 MB (2 GB) for RAM
<img src="https://i.imgur.com/WuAefLk.gif" height="80%" width="80%" alt="Configure VM"/>
<br/>

Step 6: Click on storage and ‘add optical drive’, then select the Windows server 2019 iso as shown below. <br/>
<img src="https://i.imgur.com/4YbZzWZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/D7EjDCJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 7: In General, in the features tab change ‘shared clipboard’ and ‘drag-and-drop’ to ‘bi-directional’. This will allow us to copy + paste and drag/drop files from our actual machine to the VM.  <br/>
<img src="https://i.imgur.com/ScpWhqX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 8: Go to the network tab, ensure the first network adapter is attached to NAT, and enable the second adapter and attach it to the internal network. <br/>
<img src="https://i.imgur.com/wjCtZgj.gif" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 9: We are finally ready to launch our VM. Choose language, time, and keyboard preference on the next page click “Install now’. Make sure you choose ‘Windows Server 2019 Standard Evaluation (Desktop Experience) as shown below. This will give us the GUI. After that select custom install. The installation will take a few minutes.   <br/>
<img src="https://i.imgur.com/7vLznF3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 10: Set password and proceed to login, when prompted to hit ‘CTRL + ALT + Delete’ go to input < keyboard < insert ctrl + alt + delete, as shown below.   <br/>
<img src="https://i.imgur.com/OhYvxY7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/hZN9CUJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 11: Navigate to network < ethernet < change adapter options. Right click each ethernet < status < details. Look at the IPv4 address to determine if it is internet facing or internal. If the IP address starts with 169 this is an APIPA address meaning it does not have access to the internet, we will rename this ‘internal’. The other IP address will start with 10, this is connected to the internet, we will rename it ‘internet’.  <br/>
<img src="https://i.imgur.com/KPU7BIL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/gA2PJ5i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Step 12: Right click on the internal network < properties < Internet Protocol Version 4 (TCP/IPv4).  Select ‘use the following ip address’ to manually assign a static ip address to the server. Set the IP address as 172.16.0.1(IP addresses from 172.16.0.0-172.31.255.255 are private), the subnet mask to 255.255.255.0, and the preferred dns to 127.0.0.1 (Since the server will host the DNS service we use the loopback address).  <br/>
<img src="https://i.imgur.com/7du8eT3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Step 13: We will now install the AD domain services.  In the server manager dashboard click ‘add roles and features’ < next < next < select the server < next < active directory domain services < next < next < next < install.    <br/>
<img src="https://i.imgur.com/0JPByEL.gif" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Step 14: In order to promote the server to a domain controller, click on the flag that has a notification next to it in the server manager dashboard. Click ‘add new forest’ and name the domain, I chose ‘mydomain.com’. Click next and enter a password. Keep clicking next and then install. Once it finishes it will restart the computer. When you login again you will see the domain name and the admin name.  <br/>
<img src="https://i.imgur.com/xCIt8sQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Kke6P8H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Step 15: Open active directory users and computers from start, we will create our first OU (organizational unit) and object (user). Right click my domain.com < new < organization unit. Name it ‘Admins2’ then click new < user. Enter first/last name and password. We have now created our first user. In order to make it a domain admin right click, go to properties < member of < add < type ‘domain admins’ < check name < apply < ok. We will now logout and choose ‘other user’ and login using our newly created admin account. <br/>
<img src="https://i.imgur.com/SRcgNxf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/lSdvOSc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Step 16: We will now install RAS which will allow our windows 10 client to access the internet through the domain controller. In the server manager dashboard click ‘add roles and features’ < next < next < select the server < next < remote access < next < routing and direct access and VPN < next  < next < next < install.     <br/>
<img src="https://i.imgur.com/QLgoBYn.gif" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Step 17: In the server manager dashboard click on tools < routing and remote access < DC (local) < configure and enable routing and remote access < next < NAT < internet < next < finish. This allows our domain controller to act as a router for our windows client users. 
Tip: If the two connections don’t appear, close the wizard and try again. <br/>
<img src="https://i.imgur.com/yeE1FAC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />

Step 18: We will now install DHCP which will allow our DC to give our clients ip addresses.  In the server manager dashboard click ‘add roles and features’ < next < next < select the server < next < DHCP < add features < next < next < next < install.      <br/>
<img src="https://i.imgur.com/XyhPAvn.gif" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />







</p>
