# Detecting Cross Site Scripting (XSS) Attacks
## What is Cross-Site Scripting (XSS)?
Cross-site scripting (XSS) is a type of injection-based web security vulnerability that can be incorporated into legitimate web applications, allowing malicious code to be executed.

Today, most frameworks used to develop web applications have taken preventative measures against cross-site scripting attacks. However, we still see XSS vulnerabilities today because frameworks are sometimes not used, or the framework itself has an XSS vulnerability and the data coming from the user is not sanitized.

## Types of XSS
There are 3 types of XSS. These are:
- Reflected XSS (Non-Persistent): This is a non-persistent type of XSS where the XSS payload must be present in the request. It is the most common type of XSS.
- Stored XSS (Persistent): This type of XSS is where the attacker can permanently upload the XSS payload to the web application. Compared to other types, Stored XSS is the most dangerous type of XSS.
- DOM Based XSS: DOM Based XSS is an XSS attack where the attack payload is executed as a result of modifying the DOM "environment" in the victim's browser used by the original client-side script so that the client-side code runs in an "unexpected" manner. (OWASP)
