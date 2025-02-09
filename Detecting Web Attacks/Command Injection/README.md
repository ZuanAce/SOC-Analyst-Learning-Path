# Detecting Command Injection Attacks

## What are Command Injection Attacks?
Command injection attacks are attacks that occur when data received from a user is not sanitized and is passed directly to the operating system shell.

Attackers exploit command injection vulnerabilities to execute commands directly on the operating system. Since the attacker's priority is to take control of the system, these vulnerabilities are more critical than other vulnerabilities.

A misconfigured web application would grant the attacker access with admin rights because the command the attacker sends uses the rights of the web application user.

## How does Command Injection work?
Command injection vulnerabilities occur when the data received from the user is not sanitized. Let's examine command injection vulnerabilities with an example.

Suppose we have a basic web application that copies the user's file to the "/tmp" folder. The web application code is shown below:

![image](https://github.com/user-attachments/assets/0ed6e73e-2781-470e-bf6a-3d210329b34b)

Under normal circumstances, if used correctly, the application will work normally. For example, if we upload a file called "letsdefend.txt", it will successfully copy the file to the "/tmp" folder.

So what if we upload a file called "letsdefend;ls;.txt"? The command would be:

Command: cp letsdefend;ls;.txt

The ";" indicates that the command has ended. So if we look at the payload above, there are three different commands that the operating system executes. These are:
- cp letsdefend
- ls
- .txt

![image](https://github.com/user-attachments/assets/e8690d4f-96be-4737-b3f2-d16d2a0d348f)

The first command is for the copying process, but if the parameters are not entered correctly it will not work correctly.

Command #2 is the directory listing command that the attacker wants to execute. The user does not receive the command output, so the attacker cannot see the files in the directory, but the operating system successfully executes the command.

If the operating system tries to run command number 3, it will get an error message because there is no ".txt" command.

As you can see, the code has been executed in the web server's operating system. So what if the attacker were to upload a file called "letsdefend;shutdown;.txt"? The operating system would shut down and the web application would not be able to function.

With the correct payload, the attacker can create a reverse shell in the operating system.

## How attackers can exploit Command Injection Attacks
Attackers can execute commands on an operating system by exploiting command injection vulnerabilities. This means that the web application and all other components on the server are at risk.

## How to Prevent Command Injection
Always sanitize data you receive from a user: Never trust anything you receive from a user. Not even a file name!
Limit user privileges: Whenever possible, set web application user rights at a lower level. Few web applications require users to have administrator rights. 
Use virtualization technologies such as dockers.

## Detecting Command Injection Attacks
I think we all understand the criticality of the command injection vulnerability. If such a critical vulnerability is exploited and goes undetected, the targeted company can lose a great deal of money and reputation.

So how do we detect command injection attacks?

Actually, there is more than one way. These are:
- When examining a web request, look at all areas: The command injection vulnerability may be in different areas depending on how the web application works. Therefore, you should check all areas of the web request.
- Look for keywords related to the terminal language: Check the data received from the user for keywords related to terminal commands such as dir, ls, cp, cat, type, etc.
- Learn about commonly used command injection payloads: When attackers discover a command injection vulnerability, they usually create a reverse shell to make their work easier. Therefore, knowing commonly used command injection payloads will make it easier to detect a command injection attack.

----

## Questions

1. Note: Use the "/root/Desktop/QuestionFiles/Command_Injection_Web_Attacks.rar" file for solving the questions below.

   Question: What is the date the command injection attack was initiated?

   File Password: access

   Answer Format: 01/Mar/2022:12:00:00

   `Answer: 01/Mar/2022:09:03:33`

2. What is the IP address of the attacker who performed the Command Injection attack?

   `Answer: 192.168.31.156`


3. Was the Command Injection attack successful?

   `Answer: N`
