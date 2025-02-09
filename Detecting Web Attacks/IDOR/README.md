# Detecting Insecure Direct Object Reference (IDOR) Attacks
## What is IDOR?
Insecure Direct Object Reference (IDOR) is a vulnerability caused by the absence or improper use of an authorization mechanism. It allows one person to access an object that belongs to another.

IDOR, or "Broken Access Control", is the number one web application vulnerability listed in the 2021 OWASP.

## How IDOR Works
IDOR is not a vulnerability caused by poor sanitation like other web application-based vulnerabilities. The attacker manipulates the parameters sent to the web application, gains access to an object that doesn't belong to him, and is then able to read, modify, or delete the contents.

Here’s an example to better understand how the IDOR vulnerability is exploited.

Imagine a simple web application. It retrieves the “id” variable from the user and then displays data that belongs to the user who made the request.

URL: https://letsdefend.io/get_user_information?id=1

When a request like the one above is made in our web application, it displays the information of the user with an id value of 1.

If I am the user who made the request and my ID value is 1, everything will work normally. When I make the request, I see my personal information.

But what happens if we make a request with 2 as the “id” parameter? Or 3?

If the web application does not check that the "id" value in the request belongs to the person making the request, then anyone can make that request and see the user's information. This web vulnerability is called IDOR.

Attackers can access items that do not belong to them by changing parameters such as the "id". The type of information they can access may vary depending on the web application, but either way, you wouldn't want anyone to access your personal information, so this is very critical.

## How Attackers Take Advantage of IDOR Attacks
What an attacker can do is limited by the scope of an IDOR vulnerability. However, the most common areas are usually pages where a user's information is received. If an attacker were to exploit an IDOR vulnerability, they could:
- Steal personal information
- Access unauthorized documents 
- Take unauthorized actions (such as deleting, modifying)

## How to Prevent IDOR
Always check that the person making the request is authorized to provide a secure environment without an IDOR vulnerability.

In addition, unnecessary parameters should be removed and only the minimum number of parameters should be taken from the user. If we think about the previous example, we don't need to get the "id" parameter. Instead of getting the "id" parameter from the user, we can use the session information to identify the person who made the request.


## Detecting IDOR Attacks
IDOR attacks are harder to detect than other attacks. This is because it does not have certain payloads such as SQL injection and XSS.

HTTP responses would help identify IDOR attacks. However, HTTP responses are not logged for several reasons. This makes it more difficult to identify IDOR attacks.

A number of methods can be used to identify IDOR attacks. These are:
- Check all parameters: An IDOR vulnerability can occur in any parameter. Therefore, do not forget to check all parameters.
- Look at the number of requests made to the same page: When attackers discover an IDOR vulnerability, they usually want to access the information of all the other users, so they typically perform a brute-force attack. This is why you may see many requests for the same page from one source.
- Try to find a pattern: Attackers will plan a brute-force attack to reach all objects. Since they will be performing the attack on successive and predictable values, such as whole numbers, you can try to find a pattern in the requests you see. For example, if you see requests like id=1, id=2, id=3, you might be suspicious.

----

## Questions
1. Note: Use the "/root/Desktop/QuestionFiles/IDOR_Web_Attacks.rar" file for solving the questions below.

   Question: What is the IP address of the attacker who carried out the IDOR attack?

   File Password: access

   `Answer: 192.168.31.174`

2. What is the date when the attack started?

   `Answer: 01/Mar/2022:11:42:32`

3. Was the attack successful?

   `Answer: Y`

4. Was the attack carried out by an automated tool?

   `Answer: N`
