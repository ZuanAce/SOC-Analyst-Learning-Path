# EDR - Endpoint Detection and Response
A SOC analyst must spend a significant amount of time using EDR when performing analysis on an endpoint device. The following sections discuss why EDR is beneficial to SOC analysts and how to use it effectively.

## What is EDR?
Endpoint Detection and Response (EDR), also known as Endpoint Threat Detection and Response (ETDR), is an integrated endpoint security solution that combines continuous, real-time monitoring and collection of endpoint data with rules-based automated response and analysis capabilities. (Definition source: mcafee.com)

## Analysis with EDR
Some EDR solutions commonly used in the workplace: CarbonBlack, SentinelOne, and FireEye HX.

To understand what you can do with EDR as an analyst, let's take a look at "Endpoint Security" on LetsDefend.

As you can see in the image, the accessible endpoint devices are listed on the left. You can search for endpoints in the search bar, or if there is an IOC (an IP address, file hash, process name, etc.), we can perform a search across all hosts.

The right side displays general information about the device and shows sections such as Browser History, Network Connections, and Process List.

### Live Investigation
Next, you can click the Connect button and access the machine itself to continue the analysis.

### Containment
You need to isolate a hacked machine from the network. There are two important reasons for doing this: to prevent the attacker from connecting to the internal network and moving around the internal network.

Therefore, the device should be isolated from the internal and external networks until the vulnerabilities are repaired and the device is ready for use. You can ensure isolation by using the containment feature of EDR solutions. This feature allows the selected device to communicate solely with the EDR center. This means that even though the device is isolated from the network, you can continue your analysis.

## Questions
1. What is the hostname of the device where the “nmap” file with a hash value of “83e0cfc95de1153d405e839e53d408f5” is executed?
   ![image](https://github.com/user-attachments/assets/bd2d7fa8-7c9f-4446-b867-d7343a32e85d)

   `Answer: EricProd`

3. A "Ps1.hta" file was executed on a device with the hostname "Roberto". What is the complete CMD command?
   ![image](https://github.com/user-attachments/assets/717b5887-a9ba-40f4-9093-c51a3bdadc9c)

   `Answer: C:/Windows/System32/mshta.exe C:/Users/roberto/Desktop/Ps1.hta`

