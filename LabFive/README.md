# Lab 5 - Security Onion 

## Overview
In this lab, we will: 
- Understand the capabilities of Security Onion in intrusion detection, security monitoring, and log management.
- Learn about the role of Security Onion in a Security Operations Center (SOC) and how it can enhance network security.
- Gain practical experience in utilizing Security Onion as a SOC Analyst to identify and respond to potential security incidents.



## Lab Environment Setup

<img src="https://github.com/xyliatgithub/EN650654-2023/blob/main/LabFive/Lab%205%20-%20Network%20Setup%20.png" width="1000">


In this lab, we will have two networks: 
For enhanced security in an enterprise setting, it is a common practice to separate the management traffic and production traffic.

1. **Management Network:** A dedicated network can be used only for administrative access and management of network resources, such as switches, servers, and routers. This network is separate from the production network and provides enhanced security in an enterprise setting.

2. **Monitor Network:** In an enterprise setting we should monitor the production network. This is done using Intrusion Detection Systems to monitor the production network and generate alerts for any malicious, anomalous, or otherwise suspicious traffic. 

You will also use five VMs: the Analyst VM connected to the Management Network, and the Attacker, Server, and User VMs connected to the Monitor Network. The Security Onion VM will be connected to both networks.

## Lab Instructions 
Please note that the minimum hardware requirements for this lab exceed the capabilities of most personal machines. So you may need to use one of the machines in MSSI Computer Lab to perform the lab tasks. Please follow all the documents **in the following order**:

1. **[Importing the Analyst VM](https://github.com/xyliatgithub/EN650654-2023/blob/main/LabFive/Importing%20the%20Analyst%20VM.pdf)** Follow this manual to import and configure the Analyst VM.
2. **[Installing Security Onion VM](https://github.com/xyliatgithub/EN650654-2023/blob/main/LabFive/Installing%20Security%20Onion%20VM.pdf)** Follow this manual to install and configure Security Onion VM.
3. **[Setting up other VMs](https://github.com/xyliatgithub/EN650654-2023/blob/main/LabFive/Setting%20up%20other%20VMs.pdf)** Follow this manual to set up and configure the Attacker, Server, and User VMs.
4. **[Security Onion Console](https://github.com/xyliatgithub/EN650654-2023/blob/main/LabFive/Security%20Onion%20Console.pdf)** Explore Security Onion Console.
5. **[NIDS Section](https://github.com/xyliatgithub/EN650654-2023/blob/main/LabFive/NIDS%20Section.pdf)** Examine how Security Onion could function as a Network-Based Intrusion Detection System. 
6. **[HIDS Section](https://github.com/xyliatgithub/EN650654-2023/blob/main/LabFive/HIDS%20Section.pdf)** Examine how Security Onion could be used as a Host-Based Intrusion Detection System.

## Grading (80 points)
Please take screenshots periodically and regularly and include them in your report. They not only serve as evidence of completion but also help the grader understand what you try to achieve. Add adequate explanation as needed. See the lab submission example for what it should look like.
* Completeness (60 pts): All the steps as instructed in the lab manual must be included in the report with adequate evidence.
* Presentation (20 pts): The report must be clear and correct in organization and writing with adequate explanation.
