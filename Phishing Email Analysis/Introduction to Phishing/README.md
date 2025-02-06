# Introduction to Phishing
A phishing attack is a type of attack that usually aims to steal the user's personal information by tricking them into clicking on malicious links in emails or running malicious files on their computer.

Phishing attacks fall into the "Delivery" phase of the Cyber Kill Chain model created to analyze cyber-attacks. The 'delivery' phase is where the attacker transfers the pre-arranged malicious content to the victim systems/people.

The attackers usually aim to get victims to click on the malicious link in the email by using tricky phrases such as "you have won a gift", "don't miss out on the big discount", "if you don't click on the link in the email your account will be suspended".

----

# Information Gathering
## Spoofing
Because emails do not necessarily have an authentication mechanism, attackers can send emails in the name of someone else. Attackers can do this by using a technique called spoofing to make the user believe that the incoming email is reliable. Several protocols have been created to prevent the email spoofing technique. The SPF, DKIM, and DMARC protocols can be used to determine whether the sender's address is fake or real. Some email programs check emails automatically. However, the use of these protocols is not mandatory and can cause problems in some cases.
- Sender Policy Framework (SPF)
- DomainKeys Identified Mail (DKIM)

To manually determine if a mail is spoofed or not, the SMTP address of the mail should first be identified. The domain's SPF, DKIM, DMARC, and MX records can be obtained using tools such as Mxtoolbox. Comparing this information will tell you if the email is spoofed or not.

As large institutions using their own mail servers will have their own IP addresses, you can check whether the SMTP address belongs to that institution or not by looking at the Whois records of the SMTP IP address.

It is also worth noting that even if the sender's address is not spoofed, we cannot say that the email is safe. Harmful emails can be sent in the name of trusted individuals by hacking corporate/personal email addresses. Such cyber-attacks have happened in the past, so it is always worth considering the possibility.

## E-mail Traffic Analysis
Many parameters are needed to analyze a phishing attack. The following parameters can give us an idea of the size of the attack and the target audience if we perform a search on the mail gateway.
- Sender Address(info@letsdefend.io)
- SMTP IP Address(127.0.0.1)
- @letsdefend.io (domain base)
- letsdefend (In addition to the Gmail account, the attacker may have sent from the Hotmail account)
- Subject (sender address and SMTP address may be constantly changing)

In addition to the email numbers, it is necessary to know the recipients' addresses and time information in the search results. If malicious emails are constantly being forwarded to the same users, their email addresses may have somehow been leaked and shared on sites such as PasteBin.

Attackers can find email addresses using the Harvester tool on Kali Linux. Posting personal email addresses on websites could provide a potential attack vector for attackers, so it is recommended that such information is not explicitly shared.

----

# What is an Email Header and How to Read Them?
## What is an Email Header?

The header is a section of the email containing information such as sender, recipient, and date. There are also components such as 'Return-Path', 'Reply-To', and 'Received'. 


