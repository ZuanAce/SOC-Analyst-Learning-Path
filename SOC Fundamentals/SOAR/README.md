# SOAR (Security Orchestration Automation and Response)

SOAR stands for Security Orchestration Automation and Response. It enables security products and tools in an environment to work together, streamlining the tasks of SOC team members. For example, it will automatically search VirusTotal for the source IP of a SIEM alert, reducing the workload of the SOC analyst.

Some SOAR products commonly used in the industry:
- Splunk Phantom
- IBM Resilient
- Logsign
- Demisto

## SOAR Capabilities
- Threat Intelligence
- EDR
- Security Operations Automation
- Playbook Management
- Vulnerability Management
- Case Management based Incident Response

## SOAR Benefits
- Saves Time: automate process such as IP address reputation control, hash query, sacnning an acquired file in a sandbox environment
- Centralization: It allows you to use different security tools in your environment (sandbox, log management, 3rd party tools, etc.) by providing an all-in-one software. These tools are integrated into the SOAR solution and can be used on the same platform.

## Playbooks
You can easily investigate SIEM alerts using playbooks created for different scenarios within SOAR. Even if you don't know or remember all the procedures, you can perform an analysis by following the steps outlined in the playbooks

In addition, these playbooks help ensure that the entire SOC team is on the same page when performing their analysis. For example, all team members need to check IP reputation, so if one team member is not checking it and the others are, this is an undesirable situation. We can avoid this situation by adding this step to the playbook.

## LetsDefend and SOAR
You can think of "Case Management" as the same as SOAR. On the SIEM (monitoring) page, you can open tickets for the cases you created. When you look at the page, the first thing you see is a list of open and closed cases.

If you click on any open case, you will see an automatically assigned playbook. You can investigate the associated SIEM (monitoring) alert following this playbook.

## Threat Intelligence Feed
 SOC team should be immediately aware of the latest threats and take the necessary precautions. To meet this need, threat intelligence feeds are created. As a SOC analyst, you can use these feeds to guide your investigations.

A Threat Intelligence Feed is data (such as malware hashes, C2 (Command&Control) domain/IP addresses etc.) provided by a third party company.

Looking at LetsDefend's Threat Intel page, you can see many types of data (hash, IP, etc.)

The data here consists of artifacts from previous malicious activity. It could be the hash of malware or the IP address of a command and control center. As a SOC analyst, you need to search threat intelligence feeds to determine if a hash file at hand has ever been used in a malicious scenario in the past.

Here are some free and popular sources you can use:
- VirusTotal
- Talos Intelligence

### If data you run through feeds does not show up
Let's say you ran a hash of an .exe in VirusTotal and in the past you didn't find anything suspicious about it. In this case, you should not just assume that the file is clean, that would be a mistake. A SOC analyst should carefully perform the necessary file analysis (static/dynamic).

### We shouldn’t forget that IP addresses can change hands.
For example, let's say an attacker created a server on AWS (Amazon Web Services) and used it as a command and control center. Then various threat intelligence feeds listed that IP address as a malicious address.

2 months later, the attacker shut down the server and someone else moved their personal blog to that server. This doesn't mean that people who visited the blog were exposed to malicious content. The fact that this IP address has been used for malicious purposes in the past does not mean that it contains malicious content.

----

## Questions
1. What is the data source of the "e1def6e8ab4b5bcb650037df234e2973" hash on the threat intel page?
   ![image](https://github.com/user-attachments/assets/70850d01-4066-46ed-b3ab-9446a4229b87)

   `Answer: AbuseCH`
