# SIEM and Analyst Relationship

## What is SIEM?
SIEM is a security solution that combines security information and event management, which involves real-time logging of events in an environment. The ultimate purpose of event logging is to detect security threats.

Overall, SIEM products have a lot of features. The ones that interest us most as SOC analysts are those that collect and filter data and provide alerts for suspicious events.

Example alert: If someone on a Windows operating system tries to enter 20 incorrect passwords in 10 seconds, this is suspicious activity. It is unlikely that someone who has forgotten their password would try to re-enter it that many times in such a short period of time. So we create a SIEM rule/filter to detect such activity that exceeds the threshold. Based on this SIEM rule, an alert will be generated when such a situation occurs.

Some popular SIEM solutions: IBM QRadar, ArcSight ESM, FortiSIEM, Splunk, etc. To get a better picture, you can visit the “Monitoring” page on LetsDefend.

## Relationship Between a SOC Analyst and SIEM
Although SIEM solutions have many features, SOC analysts typically only track alerts. There are other groups/people responsible for developing configurations and rule correlations.

As mentioned above, alerts are generated from data that passes through filters. Alerts are first analyzed by a SOC analyst. This is where a SOC analyst's job in the security operations center begins. In essence, they have to determine whether the generated alert is a real threat or a false alert.

For a better understanding, let's go back to the "Monitoring" page; as you can see below, there are various alerts on the SIEM interface. A SOC analyst should analyze the details related to these alerts with the help of other SOC products (such as EDR, Log Management, Threat Intelligence Feed, etc.) and ultimately determine whether they are real threats or not.

You can view newly created alerts in the "Main Channel" and think of this channel as a shared channel. Your teammates are not visible in this simulation, but in a real work scenario, your teammates will be able to see this panel. After you select the alert you want to work on, click the Take Ownership button in the Action area to take ownership of the alert and direct it to the Investigation Channel. This way, your teammates can see which alert you are actively working on. At the same time, this will help them see which alerts you are already working on so they can select other alerts. This way, your team can quickly review all alerts.

When you click on the alert, you can see the details of the alert. This allows you to gather the information (hostname, IP address, file hash information, etc.) required to investigate.

## Questions
1. When you close an alert, which channel can you access it from?

   `Answer: Closed Alerts`
