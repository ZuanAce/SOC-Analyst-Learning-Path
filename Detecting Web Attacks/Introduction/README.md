# Introduction
## What are web attacks?
Web applications are applications that provide services to users through a browser interface. Today, web applications make up a large part of internet usage. Sites such as Google, Facebook, and YouTube (excluding their mobile applications) are actually web applications.

Because web applications serve as the interface to the internet for many organizations, they can be exploited by attackers to gain access to devices, steal personal data, or cause service disruptions, resulting in significant financial damage.

A study by Acunetix found that 75% of all cyber-attacks were at the web application level.

Below are some of the attack methods used to infiltrate web applications. We will cover these methods in our Web Attacks 101 course, explaining what they are, how and why attackers use them, and how we can detect such activity.
- SQL Injection
- Cross Site Scripting
- Command Injection
- IDOR
- RFI & LFI
- File Upload (Web Shell)

----

# Why Detecting Web Attacks Important
If you look at the average person's daily routine, you'll see that they use a variety of web applications, such as Spotify to listen to music, YouTube to watch videos, and Twitter to read tweets.

It is no surprise that attackers choose web applications as a gateway for their attacks, because all organizations have web applications, most of which contain critical data, and because today's applications are highly complex and have numerous attack vectors.

“””According to Acunetix research, 75% of cyber attacks are done at the web application level, supporting this idea.“”” 

If we examine the anatomy of an attack, we can clearly see that the best scenario is to prevent the attack in its first phase. This is why there are various security measures aimed at preventing and detecting threats against web applications (WAF, IPS, SIEM rules...).

It is essential that a SOC analyst detects and takes precautions against these web application-based attacks that are favored by attackers.

----

# OWASP
The Open Web Application Security Project (OWASP) is a non-profit foundation dedicated to improving software security. Without a doubt, OWASP is one of the best resources for information on web application security.

## OWASP Top Ten
Every few years, OWASP publishes a list of the 10 web application vulnerabilities that pose the most critical security risks. The latest release was in 2021 at the time of writing.

![image](https://github.com/user-attachments/assets/2b03a52a-98af-46bb-843f-ea2dd6ff0995)

----

How Web Applications Work
To identify an anomaly, we should first understand how the technology works. Applications use specific protocols to communicate with each other. In this case, web applications communicate using the Hyper-Text Transfer Protocol (HTTP). Let's take a look at how the HTTP protocol works.

First of all, it's important to know that the HTTP protocol is on layer 7 of the OSI model. This means that protocols such as Ethernet, IP, TCP, and SSL are used before the HTTP protocol.

![image](https://github.com/user-attachments/assets/efacfb44-59b4-41d3-9bf6-f345c6b269f3)

HTTP communication is between the server and the client. First, the client requests a specific resource from the server. The server receives the HTTP request and sends an (HTTP response) back to the client after passing the request through certain controls and processes. The client's device receives the response and displays the requested resource in an appropriate format.

![image](https://github.com/user-attachments/assets/6be31a74-95d0-457b-b3a0-593f43d77e5f)

## HTTP Requests
An HTTP request is used to retrieve a specific resource from a web server. This resource can be an HTML file, a video, JSON data, etc. The web server's job is to process the response received and present it to the user.

All requests must conform to a standard HTTP format so that web servers can understand the request. If the request is sent in a different format, the web server will not recognize it and will return an error to the user, or the web server may not be able to provide service (which is another type of attack).

![image](https://github.com/user-attachments/assets/48e07667-0e4c-4b1c-a64c-60d93cadf8bd)

An HTTP request consists of a request line, request headers, and a request message body. The request line consists of the HTTP method and the resource requested from the web server. The request headers contain certain headers that the server will process. The request message body contains the data to be sent to the server.

The image above shows an example of an HTTP request. Let's examine this HTTP request line by line.

- The GET method indicates that the resource "/" is being requested from the server. Because there is no name, a symbol like "/" means that the main page of the web server is being requested.
- Nowadays there are web applications that belong to more than one domain found on a single web server, so browsers use the "Host" header to identify which domain the requested resource belongs to.
- When a web application wants to store information on the client's device, it stores it in a "cookie" header. Cookies are typically used to store session information. This saves you from having to re-enter your username and password when you visit a web application that requires you to log in.
- The “Upgrade-Insecure-Requests” header indicates that the client wants to communicate using encryption (SSL).
- The “User-Agent” header contains information about the client's browser and operating system. Web servers use this information to send specific HTTP responses to the client. You can find some automated vulnerability scanners by looking under this header.
- The type of data requested is in the “Accept” header.
- The type of encoding accepted by the client is found in the “Accept-Encoding” header. You can usually find the names of compression algorithms under this header.
- The “Accept-Language” header contains the client's language information. The web server uses this information to display the prepared content in the client's language.
- The “Connection” header shows how the HTTP connection is made. If there is data such as "close", it means that the TCP connection will be closed after receiving the HTTP response. If you see "keep-alive", this means that the connection will be maintained.
- An empty line is inserted between the HTTP request header and the HTTP request message body to create a partition.
- Any other data to be sent to the web application is in the Request Message Body. If the HTTP POST method is used, then the POST parameters can be found here.

## HTTP Responses
When the web server receives an HTTP request, it performs the necessary checks and processes and then sends the requested resource to the client. There is no standard process, as there are many technologies and designs involved. The server may pull data from the database depending on what the requested resource is, or it may process the incoming data. However, the HTTP Response Message must reach the client after all the processing.

An HTTP response message contains a Status Line, Response Headers, and a Response Body. The Status line contains the status code (e.g. 200: OK) and HTTP protocol information. Within the Response Header, some headers are used for a variety of purposes. The Response Body contains information about the requested resource.

If a web page has been requested, there will usually be HTML code in the Response Body. When the client receives the HTML code, the web browser will process the HTML code and display the web page.

![image](https://github.com/user-attachments/assets/33b47198-5c85-4884-b264-cf98d5989fa1)

### Status Line
The Status Line contains information about the HTTP version and the HTTP Response Status Code. The HTTP Response Status Code is used to describe the status of the request. There are many HTTP response status codes, but they can be summarized as follows:
- 100-199: Informational responses
- 200-299: Successful responses
- 300-399: Redirection messages
- 400-499: Client error responses
- 500-599: Server error responses


### Response Headers
Here are some HTTP Response Headers that you may encounter frequently:
- Date: The exact time the server sent the HTTP Response to the client.
- Connection: This indicates how the connection is handled, just like the HTTP Request header.
- Server: It informs about the operating system of the server and the version of the web server.
- Last-Modified: It provides information about when the requested resource was modified. This header is used by the caching mechanism.
- Content-Type:  The type of data being sent.
- Content-Length: The size of the data sent. 

### Response Body
The HTTP response body contains the resource sent by the server and requested by the client.

----

## Questions
1. What is the name of the tool that OWASP has prepared to help scan web applications for vulnerabilities?<br>
   `Answer:zap`

2. Which area does OWASP focus on?<br>
   `Answer:A (Web Applications)`

3. What is the name of the vulnerable web application project that OWASP wrote using Node.js for security researchers to improve themselves?<br>
   `Answer: juice_shop`

4. What does the OWASP Top 10 list, published every few years, reveal?<br>
   `Answer: B) Most critical security risks to web applications`

5. What layer is HTTP on in the OSI model?<br>
   `Answer: application`

6. Which HTTP Request header contains browser and operating system information?
   `Answer: user-agent`

7. What is the HTTP Response status code that indicates the request was successful?
   `Answer: 200`

8. Which HTTP Request Method ensures that the submitted parameters do not appear in the Request URL?
   `Answer: POST`

9. Which HTTP Request header contains session tokens?
   `Answer: Cookie`





   






