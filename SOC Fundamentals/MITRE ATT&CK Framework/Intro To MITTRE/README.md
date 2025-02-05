# Introduction to MITRE

## What is MITRE?
MITRE was founded in 1958 in the USA as an organization that produces innovative solutions to advance national security in new ways and serve the public interest as an independent adviser. MITRE’s areas of work are Cybersecurity, Aerospace, AI & Machine Learning, Aviation & Transportation, Defense & Intelligence, Government Innovation, Health, Homeland Security and Telecom.

## What is MITRE ATT&CK Framework?
MITRE ATT&CK that stands for Adversarial Tactics, Techniques, and Common Knowledge is the framework of a knowledge database that was introduced by MITRE in 2013 and has been continuously developed and expanded along with the technology. It is possible to analyze cyber attacks systematically through the MITRE ATT&CK framework. Cyber attacks can be divided into certain stages and the methods used in each stage can be analyzed in depth and used in studies related to cyber security. The MITRE ATT&CK Framework is an essential resource for each and every employee in the cybersecurity industry.

## Why is the MITRE ATT&CK Framework important to SOC Analyst?
Since each step of cyber attacks is covered in detail in the MITRE ATT&CK Framework, SOC Analysts can clearly see the actions that should be taken for each stage of the cyber attack and that it as a reference. In this way, attack detection and mitigation techniques developed against cyber attacks can be used more effectively, cyber attacks can be mapped, an in-depth report can be written and the details of the attack can be archived for a later use. Since this framework provides a clear roadmap of cyber attacks, researches can be conducted on other possible cyber attacks that have not yet occurred yet to develop ways to detect or avoid them.

----

# Matrix
##vWhat is MITRE ATT&CK Matrix?
MITRE ATT&CK Matrix is a visualization method used to classify and see attack methods of cyber attackers. Matrices can be customized for almost any subject and turned into useful visuals. MITRE has created MITRE ATT&CK matrices to visualize the details of attacker behavior using the matrices.

Types of Matrices
3 different matrices have been created within the MITRE ATT&CK Framework according to the platform types:
- Enterprise Matrix
- Mobile Matrix
- ICS (Industrial Control Systems) Matrix

### Enterprise Matrix
Enterprise matrix is the first matrix created by MITRE. There are more digital systems included in this matrix and are more common than those that are included in other matrices, so there are a lot more information in this matrix than other matrices. Enterprise matrix is mainly used to understand the cyber attacks on large organizations.

There are 7 sub-matrices under the Enterprise Matrix:
- PRE
- Windows
- macOS
- Linux
- Cloud
- Network
- Containers

### Mobile Matrix
The mobile matrix is the one that was prepared for mobile devices and contains information about the cyber security of mobile devices. This matrix can be used to ensure the security of individual and corporate mobile devices. Comparing the Enterprise Matrix, it contains less information:

Mobile Matrix has 2 sub-matrices:
- Android
- iOS

### ICS Matrix
The ICS Matrix is the one that contains the information collected for the cyber security of devices in the industrial control systems. This matrix can be used to provide cyber security and analyses of an ICS.

----

# Tactics

## What is Tactic?
Tactic expresses the purpose of the cyber attacker and the reason for his action. Tactics are one of the most important MITRE ATT&CK Framework components used to group cyber attacker behaviors and see the attack steps. Tactics are in the top row of the matrix.

## Types of Tactics
Tactics often consist of general statements as they express the purpose and reason for the cyber attack. Therefore, the tactics for each matrix are highly similar.

## Enterprise Tactics
There are 14 tactics in the Enterprise matrix as in the list below:
- Reconnaissance
- Resource Development
- Initial Access
- Execution
- Persistence
- Privilege Escalation
- Defense Evasion
- Credential Access
- Discovery
- Lateral Movement
- Collection
- Command and Control
- Exfiltration
- Impact

## Mobile Tactics
There are 14 tactics in the Mobile matrix as in the list below:
- Initial Access
- Execution
- Persistence
- Privilege Escalation
- Defense Evasion
- Credential Access
- Discovery
- Lateral Movement
- Collection
- Command and Control
- Exfiltration
- Impact
- Network Effects
- Remote Service Effects

## ICS Tactics
There are 12 tactics in the ICS matrix as in the list below:
- Initial Access
- Execution
- Persistence
- Privilege Escalation
- Evasion
- Discovery
- Lateral Movement
- Collection
- Command and Control
- Inhibit Response Function
- Impair Process Control
- Impact

----

# Techniques and Sub-Techniques
## What are Techniques and Sub-Techniques?
The tactics within the matrix only show what the attackers aim and do not contain detailed information about the attacker's attack method. The techniques and sub-techniques, on the other hand show the methods used by the attacker to achieve his goal and how he conducted the attack exactly. Each technique/sub-technique is included within the matrix depending on a particular tactic.

## Types of Techniques and Sub-Techniques
Techniques are divided into 3 groups according to matrices:
- Enterprise Techniques
- Mobile Techniques
- ICS Techniques

### Enterprise Techniques
There are quite a number of enterprise techniques and are constantly updated over the time. The current number (05.02.2025) of enterprise techniques and sub-techniques is as follows:
- Techniques: 203
- Sub-techniques: 453

### Mobile Techniques
Total number of mobile techniques is less than the enterprise techniques and they are updated over the time as well. The current number (05.02.2025) of the mobile techniques and sub-techniques is as follows:
- Techniques: 73
- Sub-techniques: 46

### ICS Techniques
As with the techniques of other matrices, ICS techniques are also updated over the  time. The current number (05.02.2025) of ICS techniques and sub-techniques is as follows:
- Techniques: 83
- Sub-techniques: 0

## What is Procedure?
The procedure consists of usage examples of techniques/sub-techniques. It simply shows which tool/software was utilized during the implementation of the technique. In other words, it is the explanation of the practical information on the use of the technique.
  
----

## Questions
1. What is the name of the images on the tactic and techniques in the MITRE ATT&CK Framework?

   `Answer: Matrix`
   
2. What is the matrix of information about the cybersecurity of Windows, Linux, macOS, Azure AD and Office 365 platforms?

   `Answer: Enterprise`

3. What is the matrix that contains the information about the cyber security of Android and iOS platforms?

   `Answer: Mobile`

4. What is the ID of the "Lateral Movement" tactic in the Enterprise matrix?

   `Answer: TA008`

5. When was the "Persistence" tactic in the mobile matrix created?

   `Answer: 17 October 2018`

6. What is the name of the tactic in Enterprise, Mobile and ICS matrices which is under the techniques related to obtaining higher-level permission on the target system/network?

   `Answer: Privilege Escalation`

7. What is the name of the technique with the ID T1055 among the Enterprise techniques?

   `Answer: Process Injection`

 8. Among the Enterprise techniques, which platform is the technique with the ID T1112 for?

    `Answer: Windows`

9. Under which tactic is the "Supply Chain Compromise" technique which is among the Enterprise techniques?

    `Answer: Initial Access`



