# Detecting Cross Site Scripting (XSS) Attacks
## What is Cross-Site Scripting (XSS)?
Cross-site scripting (XSS) is a type of injection-based web security vulnerability that can be incorporated into legitimate web applications, allowing malicious code to be executed.

Today, most frameworks used to develop web applications have taken preventative measures against cross-site scripting attacks. However, we still see XSS vulnerabilities today because frameworks are sometimes not used, or the framework itself has an XSS vulnerability and the data coming from the user is not sanitized.

## Types of XSS
There are 3 types of XSS. These are:
- Reflected XSS (Non-Persistent): This is a non-persistent type of XSS where the XSS payload must be present in the request. It is the most common type of XSS.
- Stored XSS (Persistent): This type of XSS is where the attacker can permanently upload the XSS payload to the web application. Compared to other types, Stored XSS is the most dangerous type of XSS.
- DOM Based XSS: DOM Based XSS is an XSS attack where the attack payload is executed as a result of modifying the DOM "environment" in the victim's browser used by the original client-side script so that the client-side code runs in an "unexpected" manner. (OWASP)

## How does XSS work?
Like other web attack methods, XSS is a vulnerability that is caused by a lack of data sanitization. It occurs when the data received from the user is sent in the response without being sanitized.

Let's look at an example to understand XSS attacks better.  

![image](https://github.com/user-attachments/assets/668dd7b5-6948-4f4c-8a0b-bc57816e8651)

First, we'll examine the piece of code above. What it does is actually quite simple. It simply displays whatever is entered in the 'user' parameter. If we enter "LetsDefend" as the 'user' parameter, we will see the words "Hello LetsDefend".

![image](https://github.com/user-attachments/assets/8bf799de-20c0-4fd4-8e11-b15b5c4fb4a1)

So far there is no problem. If we enter the appropriate data in the user parameter, we are greeted with a warm welcome. But, as we have already seen, there is no control mechanism for the user parameter. This means that whatever we put in the "user" parameter will be included in the HTTP response we receive back.

So what would happen if we didn't enter a normal value, but instead a payload that would trigger a popup?

Payload: `<script>alert(1)</script>`

![image](https://github.com/user-attachments/assets/001cd2ee-3be4-42e8-b641-1ab22c5001e7)

Because whatever is put in the 'user' parameter is included directly in the HTTP response, the javascript code we wrote worked and a pop-up window appeared on the screen.

This is exactly how XSS works. Because the value entered by the user is not validated, the attacker can enter any javascript code and get the result they want. Another question is, what if the attacker wants to redirect the user to a malicious site?

Payload: `<script>window.location=’https://google.com’</script>`

`https://letsdefend.io/xss_example.php?user=%3Cscript%3Ewindow.location=%27https://google.com%27%3C/script%3E`

![image](https://github.com/user-attachments/assets/b991445e-736a-41b9-8bbb-8f7af74a3672)

Of course we are not going to direct you to a web application. Directing you to Google will be sufficient as an example. When the user clicks on the URL he will be directed to Google instead of the perfect LetsDefend web application. 

![image](https://github.com/user-attachments/assets/9d3779fc-c60e-448a-87d9-3e4c86748b33)

## How Attackers Take Advantage of XSS Attacks
Because XSS is a client-based attack method, it may seem less important than other attack methods, but XSS attacks and their impact should not be taken for granted.

Attackers can do the following with an XSS attack:
- Steal a user’s session information
- Capture credentials
- Etc.

## How to Prevent a XSS Vulnerability
Sanitize data coming from a user: Never trust data that you receive from a user. If user data needs to be processed and stored, it should first be encoded with "HTML Encoding" using special characters, only then can it be stored.
Use a framework: Most frameworks come with preventative measures against XSS attacks.
Use the framework correctly: Almost all frameworks used to develop web applications come with a sanitation feature, but if this is not used properly, there is still a chance for XSS vulnerabilities to occur.
Keep your framework up-to-date: Frameworks are developed by humans, so they too can contain XSS vulnerabilities. However, these types of vulnerabilities are usually patched with security updates. You should therefore make sure that you have completed the security updates for your framework on a regular basis.

## Detecting XSS Attacks
As we mentioned in the previous lesson, according to a study by Acunetix, 75% of cyber-attacks are conducted through web applications. As XSS is one of the most commonly tested vulnerabilities, you will encounter it throughout your career as a SOC analyst.
- Look for keywords: The easiest way to detect XSS attacks is to look for keywords such as "alert" and "script" that are commonly used in XSS payloads.
- Learn about commonly used XSS payloads: Attackers tend to use the same payloads to look for vulnerabilities before exploiting an XSS vulnerability. Therefore, familiarizing yourself with commonly used XSS payloads would make it easier for you to detect XSS vulnerabilities. You can examine some commonly used payloads here.
- Check for the use of special characters: Check data coming from a user to see if any special characters commonly used in XSS payloads, such as greater than (>) or less than (<), are present.

----

## Questions
1. Note: Use the "/root/Desktop/QuestionFiles/XSS_Web_Attacks.rar" file for solving the questions below.

   Question: What is the start date of the XSS attack?

   File Password: access

   Answer Format: 01/Mar/2022:12:00:00

   `Answer: 01/Mar/2022:08:53:20`


2. What is the IP address of the attacker who performed the XSS attack?

   `Answer: 192.168.31.183`

3. Was the XSS attack successful?

   `Answer: Y`

4. What is the type of XSS attack? (Reflected, Stored, Dom based)

   `Answer: Reflected`

