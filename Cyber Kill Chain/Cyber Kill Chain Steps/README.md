# Cyber Kill Chain Steps
There are several actions that an attacker can take before, during, and after a successful cyber attack. These actions are sequential, and if the attacker fails at one stage, it is not possible to execute the next step of the cyber attack. The Cyber Kill Chain model divides these stages of attackers into 7 steps. The steps of cyber attacks are depicted in the visual  below:

## Reconnaissance
The Cyber Kill Chain begins with the "Reconnaissance" step. The attacker attempts to obtain information about the target system at this step. The more knowledge an attacker has about the target system, the more the attack surface seems to him. Attack vectors for the target are disclosed in this way. The techniques employed at this stage may be divided into two subcategories:
- Passive Reconnaissance
- Active Reconnaissance

The term "Passive Reconnaissance" refers to the collecting of information from sources about the target system without physically engaging with the target system. As an instance of this, Web archive websites can be used to obtain information that is no longer available on the target system's website.

"Active Reconnaissance" refers to the method of acquiring information about a target system by engaging with it directly. By submitting a request to a web server, for instance, version information about the web server may be acquired from the response.

### Adversary
The attacker can gather information from a variety of sources using a variety of approaches during the "Reconnaissance" process. At this phase, the attacker can perform the following operations:
- Obtaining version information of servers and software belonging to the target
- Obtaining information from open sources of information about the target has previously been released
- Obtaining e-mail addresses of employees of the organization
- Obtaining internal or personal information about employees of the organization using social networking platforms
- Detection of devices that are connected to the Internet
- Detection of security vulnerabilities on servers open to access on the Internet
- Identifying the IP address block belonging to the organization
- Identification of vendors that the organization cooperates with

### Defender
Blueteams may take action in response to attackers' attempts at this stage. This reduces the amount of information that an attacker can obtain. Some methods that SOC analysts and blueteams can implement are listed below:
- Detection of areas of information disclosure with external pentest
- Obtaining leak information about the organization from Threat Intelligence sources
- Not to keep the documents providing organizational information available on the internet
- Monitoring traffic by installing security solutions such as firewalls in areas of the company that are accessible over the internet
- Instantly updating to avoid new security vulnerabilities from being exploited

----

## Weaponization
The "Weaponization" is the second step in the Cyber Kill Chain. At this stage, the attacker uses the information obtained in the previous stage to access the tools needed for the attack or develops the tool/script directly. At this stage, preparation for a cyber-attack may differ depending on the sort of attack. For example, if a phishing-type cyber attack is to be carried out, an exploit can be constructed in response to a recognized security vulnerability, or malicious email content can be generated. If the tools for the cyber attack are ready, the attacker completes this phase quickly and moves on to the next phase of the cyber attack. At this point, the attack has not yet commenced, and the victim is generally unaware of the attacker.

### Adversary
The attacker might build many alternative attack techniques or prepare the essential components for a cyber attack during the "Weaponization" process. The following are some of the processes that the attacker might employ at this stage:
- Creating malware
- Developing exploits
- Creating malicious content for use in a phishing attempt (such as an email template and a malicious document).
- Identifying the best instrument for the cyber attack

### Defender
It is not possible for SOC analysts and Blueteams to directly prevent the attack preparations of attackers at this stage. However, some measures can be taken, albeit limited. Some of these measures are as follows:
- Checking the systems on a regular basis to see if any identified security vulnerabilities exist.
- Installing security updates for the systems of the institutions as soon as possible
- Analyzing the impact of known or newly produced cyber attack tools on systems by tracking the known or newly developed attack tools and therefore being able to detect when the tool is utilized

----

## Delivery
The third step of the Cyber Kill Chain is the "Delivery" stage. At this stage, the attacker executes the cyber attack that he prepared for in the preceding phases. This is the stage where the first interaction with the victim happens. For instance, malware is uploaded to the proper environment at this step, and the victim downloads the malware from the uploaded environment to their systems. Malicious content can be conveyed to the victims' devices in various ways during the delivery phase. The methods used for delivering malicious content may differ depending on the type of attack. For instance, using email for a phishing attack may be preferred, or the malicious content in the email can be uploaded to a web address.

### Adversary
In the "Delivery" stage, the attacker can deliver a variety of cyber weapons to the victim via a variety of methods. At this stage, the attacker can carry out the following operations:
- Delivering a malicious URL via email
- Delivering malware as a file attachment via email
- Delivering malware through the website
- Delivering the malicious URL via social media
- Delivering malware via social media
- Uploading the malware directly to the target server (if direct access to the server is possible)
- Physically installing or enabling the installation of malware directly to the target system via a USB device


### Defender
Blueteams and individual users can take plenty of precautionary measures at this stage. Although they cannot totally prevent the cyber attack from occurring, these precautions can drastically minimize the risk of a successful cyber attack. Some of these measures are listed below:
- Adopting a skeptical attitude towards URLs in email content and viewing them in a sandbox environment
- Scanning the email's attachments using antivirus software
- Using email security solution products in organizations
- Ensuring that users/institutional employees receive training on information security
- Constant monitoring of server access and recording of logs
- Effective use and management of security solutions such as Firewall
- Conducting detailed analysis of suspicious activities when needed
- Detecting anomalies and determining the initial reason

----

## Exploitation
The fourth step of the Cyber Kill Chain is the "Exploitation" stage. The attacker ensures that the malicious content provided to the victim in the previous step gets activated in this stage. During the exploitation step, the process of running the malware transmitted to the victim's device is carried out. The initial operation in the system is performed by the attacker at this stage.The exploit operation performed here is a precursor of the attack activities that will be carried out in the subsequent phases. The next phases of the cyber attack cannot be carried out if the exploit fails here for a reason, or if the delivered malware cannot be run.

### Adversary
The attacker has some basic knowledge about the program or system intended to be exploited in the target and has prepared the appropriate attack tools beforehand in the "Exploitation" stage. This is the step the attacker's exploit or tool is run/tested. This step may be failed if the exploit or tool is not suitable to be utilized on the victim's system. At this level, the attacker can perform the following operations:
- Executing the exploit that exploits the hardware vulnerability
- Executing the exploit that exploits the vulnerability of the software or operating system
- Running malware


### Defender
Defending against exploitation poses a significantly more intricate and labor-intensive task for Blueteams compared to other stages. This is primarily due to the potential encounter with previously unseen malware or exploits, which adds a layer of complexity to the defense process. To elucidate, the use of zeroday exploits can complicate the detection and prevention procedures during this phase. The following points may be considered to detect and prevent malicious activities:
- Training the employees of the organization on when it is/is not necessary to open a file uploaded on the systems and what issues should be considered
- Constantly monitoring system security operations on the assets belonging to the organization and detecting anomalies
- Tracking the security vulnerabilities published for the assets belonging to the organization, writing the appropriate monitoring rule, and detecting them when they are exploited
- Following the security updates of the assets belonging to the organization and installing them immediately
- Monitoring activities on endpoints using EDR products
- Providing secure coding training to software developers in order to prevent security vulnerabilities in locally developed applications 
- Conducting pentests on assets of the organization on a regular basis
- Regular automated vulnerability scanning and monitoring of reports
- Organizing the authorizations on the assets belonging to the institution and giving each account the authority needed

----

## Installation
The fifth phase of the Cyber Kill Chain is the "Installation" phase. At this stage, the attacker attempts to maintain persistence on the target system that was exploited. The attacker attempts to gain an access path that can be accessed at any time by installing a backdoor on the system. Because the exploited vulnerability will be patched and rendered inoperable after a certain time, the attacker must use a different method to gain access to the target system. At this point, the malware to be installed on the target device can alternatively be placed with the help of a dropper. At this point, the attacker may attempt to acquire access to a highly authorized user account in the system via privilege escalation tactics in order to assure system persistence. This is the stage at which attack preparations are carried out to achieve the ultimate aims once the cyber attack has begun.

### Adversary
In the "Installation" step, an attacker can perform a wide range of operations. The attacker can successfully perform various technological activities provided that they are constrained to their authority in the system they exploit. While performing these operations, the attacker tries to leave as few traces as possible on the system and ensure that security products do not interfere with the operations. In this manner, the attacker can remain undetected on the system for a longer period, gaining the required time to carry out the attack. At this stage, the attacker can perform the following actions:
- Install malware on the victim's device.
- Placing a backdoor on the victim's system
- Install web shell on the web server (if it is a web server).
- Adding a service, firewall rule, or scheduled task to ensure the persistence of the victim device

### Defender
The operations that Blueteams apply against attackers at this stage consist of the operations of Threat Hunting. The fact that an attacker who reached this stage is performing malicious activities on the systems indicates that the attacker cannot be detected. Therefore, whether the attacker is present or not, the SOC team should manage and execute security operations under the assumption that there is always an attacker present in the system. Security operations that can be performed at this level will depend on the current structure. The following are some activities that can be taken generally:
- To carry out Network Security Monitoring operations on all assets of the organization
- Using EDR security solutions to be aware of configuration changes applied on each endpoint
- Restricting access to critical files on systems and monitoring access
- Restricting access to critical paths on systems and monitoring access
- To allow the use of admin privileges only for mandatory situations by making authorization arrangements for users on the systems
- Detecting malicious process activities by monitoring the processes running on the systems
- Allowing only executable files with a valid signature to be run on the system
- Detect anomalies in all monitored system activities and find the root cause

----

## Command and Control (C2)
The sixth stage of the Cyber Kill Chain is the "Command and Control (C2)" step. At this point, the attacker has completed several crucial tasks of the attack and has prepared the Command and Control (C2) server to deliver commands to the system. The attacker can send remote commands to the system and execute them at this step.

### Adversary
In the "Command and Control (C2)" stage, what the attacker does is establish contact between C2 and the target system. This stage does not include the execution of the actions targeted by the attacker. Once the C2 communication is complete, the attacker will proceed to carry out malicious activities. 

Briefly, what the attacker does at this stage is as follows:
- Configuring C2 Server to communicate with the victim
- Implementing the necessary actions on the victim's device to make its contact with C2 possible.

### Defender
Although there is no specific action for blue teams at this stage, general security monitoring and detection techniques and practices within the context of C2 communication should be considered. Blueteams should take the appropriate steps to recognize and prevent potential C2 network traffic flow. The following are some steps to be taken:
- To determine whether the known C2 tools are available on systems
- Blocking C2 server IP addresses from Cyber Threat Intelligence sources through security products such as Firewall
- To detect network traffic that may be C2 communication with Network Security Monitoring on the system

----

## Actions on Objectives
"Actions on Objectives" is the seventh and final step of the Cyber Kill Chain. At this point, the attacker takes the actions planned at the first stages of the cyber attack. The attacker goes through numerous phases each of which needs to be accomplished succesfully before getting to this step. Therefore, the attacker can carry on the desired operations on the system.

### Adversary
When the attackers reach this level, their targeted moves may differ. At this step, the attackers’ actions are determined by their purpose and motivation. If the attacker's primary goal is to cause system damage, they may delete critical information, as an example. The following are some of the steps that the attacker can conduct at this stage:
- To Encrypt files on the system with the help of ransomware
- To exfiltrate critical information/documents within the system
- Damaging the system by deleting critical information in the system
- To become able to apply more authorized operations with privilege escalation operations and to expand the scope of the cyber attack by providing access to other machines in the network
- Collecting user credentials to gain access to another device in the network
- Collecting information within the system
- Changing or manipulating the information in the system


Defender
At this stage, blue teams may need to take different actions based on each particular process to detect and stop attacker activity. First and foremost, the system must be regularly monitored. It may be possible to identify malicious activity on the system in this way. After the detection phase, the detected action should be followed by the appropriate action. One of the most fundamental measures that SOC teams may take is to prevent attackers from exfiltrating data from the organization to outside.  Because data leakage is one of the most common cyber attack outcomes today. The following are some measures that are to be taken at this stage:
- Detecting anomalies in network traffic
- Restricting network access to the outside and monitoring it continuously
- Restricting access to files/folders containing critical information and controlling access regularly
- Restricting the authorization of access to databases containing critical information and continuously monitoring access
- Using DLP products to prevent data leakage
- Detecting unauthorized access by users


----


## Questions 
1. How many steps does the Cyber Kill Chain model consist of?

   `Answer: 7`

2. What is the step in the Cyber Kill Chain model where the information gathering takes place?

   `Answer: Reconnaissance`

3. **APT Group**: Lazarus Group-APT38 | **Year of Cyber Attack Detection**: 2019
   Real-life Attack Scenario:
   - The APT38 group has targeted an institution in the financial sector for a cyber attack.
   - Information was collected by conducting reconnaissance operations for several days on the organization’s website determined as the target of the cyber attack.
   - A security vulnerability with the code "CVE-2019-0604" has been found in the organization's use of Microsoft SharePoint product.
   - The identified security vulnerability was exploited.
   - After the successful exploit, the "Powershell Empire" backdoor was deployed to the target system.
   Question: The Real-life attack Scenario items above explain an aspect of an actual cyber attack. Based solely on this information, what is the number of distinct actions taken during the "Reconnaissance" phase, which is the first step of the Cyber Kill Chain?

   `Answer: 3`

4. Attack Scenario:
   - An APT group selected a telecom organization as the target of a cyber attack.
   - E-mail addresses of the selected organization were collected through social media and open sources.
   - *A phishing e-mail template was generated to be sent to the e-mail addresses of the organization's employees based on the information obtained.*
   - *A Word document titled "Salaries.docx" containing malicious macro code was created to be included in the email attachment.*
   - The prepared phishing e-mail was sent to the victim e-mail accounts on the specified date.
   - The e-mail was viewed by some employees of the organization and the malicious Word document was downloaded.
   - The malicious Word document that the victim had downloaded was opened, and the macro code contained therein was run.
   - The ransomware was installed and ran on the victim's device using malicious powershell code in the macro code.
   
   Question: How many separate activities were performed in the "Weaponization" phase, the second step of the Cyber Kill Chain, according to the Attack Scenario items above?

   `Answer: 2`

5. Attack Scenario:
   - An APT group targeted a defense sector institution with a cyber attack.
   - The IP addresses of the selected organization were detected via Shodan and Zoomeye.
   - According to the information obtained from open sources, it was learned that the organization uses the Windows operating system.
   - Malware was embedded in "putty.exe" a legitimate tool to run on Windows machines in the organization, with the help of the Metasploit tool.
   - This malware was transferred to several different USB sticks.
   - The USB sticks were left on a nearby sidewalk to the institution used by the employees before work.
   - Shortly after starting work, a curious employee plugged the USB stick into a company computer connected to the corporate network.
   - He/She executed the program named "putty.exe" on the USB stick.
   - After the program was executed, the attacker was able to temporarily execute remote commands on the company computer in the organization via the reverse connection.
   - The attacker added a new scheduled task on the Windows machine to ensure persistence.
   - The EDR product on Windows marked the added scheduled task as suspicious.
   - The SOC analyst noticed an alert named "Suspicious Scheduled Task Detected" on their security monitor.
   - After analyzing the alert, the SOC analyst took the necessary actions and prevented the cyber-attack from moving to further stages.
   
   Question: According to the Attack Scenario items above, how many different actions were performed in the "Delivery" phase, the third step of the Cyber Kill Chain?

   `Answer: 2 (6 and 7)`
   
   Question: How many separate activities were performed in the "Weaponization" phase, the second step of the Cyber Kill Chain, according to the Attack Scenario items above?

   `Answer: 2 (4 and 5)`

6. Detection Scenario:

   The EDR product detected malware on a machine within the organization. The SOC analyst examined the machine and determined that the malware was not executed and no malicious system activity occurred on the machine.

   Question: According to the above detection scenario, what is the Cyber Kill Chain step where the attacker fails and the attack is detected?

   `Answer: 4 (Exploitation)`

7. Detection Scenario: In its network connections, a Windows machine within the organization appeared to have successfully established a connection to a suspicious IP address outside the organization. With this connection, the SOC analyst determined that the attacker was able to execute remote commands on the Windows machine.
  
   Question: What is the last Cyber Kill Chain step in which the attacker is successful, according to the aforementioned detection scenario?

   `Answer: 6 (C2)`

8. The usage of the "SDelete" tool for data deletion by the APT group "Cobalt Group" is an activity at which stage of the Cyber Kill Chain?

   `Answer: 7`
