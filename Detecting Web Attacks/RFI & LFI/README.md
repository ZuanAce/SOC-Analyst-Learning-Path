# Detecting RFI & LFI Attacks
## What is Local File Inclusion (LFI)?
Local File Inclusion (LFI), is the security vulnerability that occurs when a file is included without sanitizing the data obtained from a user. It differs from RFI because the file that is intended to be included is on the same web server that the web application is hosted on.

Attackers can read sensitive files on the web server, they can see the files containing passwords that would allow them to access the server remotely.

## What is Remote File Inclusion (RFI)?
Remote File Inclusion (RFI) is a vulnerability that occurs when a file is included without sanitizing the data received from a user. It differs from LFI because the included file is hosted on another server.

Attackers lure victims through websites on remote servers and trick them into running malicious code on the servers they have prepared.

## How does LFI & RFI work?
Like most web application-based vulnerabilities, LFI and RFI have vulnerabilities caused by the failure to sanitize data received from a user.

So far we have learned that SQL injection vulnerabilities occur when data received from a user is entered into SQL queries; Command Injection vulnerabilities occur when data received from a user is executed directly in the system shell; IDOR vulnerabilities occur when data received from a user is used to directly access objects. RFI and LFI vulnerabilities arise when data received from a user is used directly in the system or to include a file on a remote server.

How could data received from a user be exploited to include a file? Web applications have become very complex over time and unfortunately, any feature that is developed can be used for malicious purposes. For example, the language setting in web applications is used to include files based on data received from a user.

![image](https://github.com/user-attachments/assets/23917847-0dae-4ca0-8a2f-c36cc7143fc4)

If we examine the piece of code in the image above, we can see that the desired website language is selected using the 'language' parameter received from the user.

In a normal situation, the web application will work as intended. For example, if "en" is entered as the "language" parameter, we will receive the file shown below.

“website/en/home.php”

However, if an attacker enters the payload below in the "language" parameter, the web application will unfortunately display the "/etc/passwd" file to the user.

Payload: /../../../../../../../../../etc/passwd%00

“website//../../../../../../../../../etc/passwd%00/home.php

"../" is used to go to the parent directory. Since the attacker does not know what directory the web application is in, he tries to use "../" to access the "root" directory. Later he names the file "/etc/passwd" and allows it to be included in the web application. The end of the string will be "%0". This way, the rest of the "/home.php" string will not be read by the web application.


## How Attackers Use RFI & LFI?
- Executing code
- Disclosure of sensitive information
- Denial of Service

## How to Prevent LFI & RFI?
The most effective way to prevent RFI and LFI attacks is to make sure that all data received from a user is sanitized before it is used. Remember that client-based controls are easily bypassed. Therefore, you should always implement your controls on both the client and server sides.


## Detecting LFI & RFI Attacks
We have already mentioned what attackers can achieve with RFI and LFI attacks. Since an organization can lose a lot of money if these vulnerabilities are exploited, we should be able to detect these attacks and take the necessary precautions.

How can we detect and prevent LFI and RFI attacks?

- When examining a web request from a user, examine all fields.
- Look for any special characters: Within the data received from users, look for notations such as '/', `.`, `\`.
- Become familiar with files commonly used in LFI attacks: In an LFI attack, the attacker reads the files on the server. Knowing the critical file names on the server will help you detect LFI attacks.
- Look for acronyms such as HTTP and HTTPS: In RFI attacks, the attacker injects the file into their own device and allows the file to run.
- To host a file, attackers usually set up a small web server on their own device and display the file using an HTTP protocol. You should therefore look for notations such as 'http' and 'https' to help you detect RFI attacks.

----

## Questions
1. Note: Use the "/root/Desktop/QuestionFiles/File_Inclusion_Web_Attacks.rar" file for solving the questions below.

   Question: What is the attacker's IP address?

   File Password: access

   `Answer: 192.168.31.174`
   
2. What is the start date of the attack?
   `Answer: 01/Mar/2022:11:58:35`

3. Was the attack successful?

   `Answer Format: N`

