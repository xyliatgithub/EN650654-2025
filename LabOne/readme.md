# Lab 1 - Local DNS Attack and Detection

In this lab assignment, you will need to setup multiple SEED lab VMs and perform an DNS attack. In addition to those tasks required by the SEED lab documentation, you also need to finish the additional tasks described below.

## Setup  

1. **Download the Pre-built VM Image**  
   - Visit [SEED Labs Lab Setup](https://seedsecuritylabs.org/labsetup.html) to download the pre-built VM image (Ubuntu 16.04, 32-bit).  

2. **VM Setup Instructions (in VirtualBox)**  
   - Refer to the [SEED VM VirtualBox Manual](https://seedsecuritylabs.org/Labs_16.04/Documents/SEEDVM_VirtualBoxManual.pdf) for detailed instructions on setting up the VM in VirtualBox.  
   - This manual also contains account information, such as usernames and passwords.  

3. **Important Notes**  
   VirtualBox is compatible with most consumer computers; however, there are exceptions for certain hardware architectures, such as Apple products with the M1 chip.  
   If you encounter difficulties with this step, consider switching to a Windows machine or using the machines available in the MSSI lab.  
   Below are instructions for setting up Ubuntu 22.04 using **VMware Fusion Player** on Apple M1 chip devices. However, please note that we have only verified the lab on Ubuntu 16.04 using VirtualBox, so there may be some differences. 

- **Using VMware Fusion Player**  
   - VirtualBox does not fully support the SEED Ubuntu 16.04 VM on Apple Silicon machines (M chips). For these devices, we recommend using **VMware Fusion Player**.  
   - Follow the instructions in the [SEED Labs VMware Fusion Guide](https://github.com/seed-labs/seed-labs/blob/master/lab-setup/apple-arm/seedvm-fusion.md) to:  
     - Install VMware Fusion Player  
     - Build the Ubuntu VM  
     - Install necessary software inside the VM  

4. **Lab Requirements**  
   - You will need to set up **three VMs** connected to the same local network.  
   - Ensure these VMs are configured in **promiscuous mode** to listen to network traffic from other VMs.  
   - After configuring one VM, you can simply clone it **two additional times** to complete the setup.  


## Instructions

1. Please follow the instructions in the DNS_Local PDF file to complete all the 9 tasks. The first three tasks are basically the environment and DNS setup.   
•	Note: You will not be able to complete all the tasks without proper setup. If you encounter any problem, please reach out to the CA for help ASAP. 

2. Please complete the following **additional tasks**:  
•	In **Task 5 - Directly Spoofing Response to User**, use tcpdump on the "User" machine to capture all the DNS packets.  
•	Since you know the IP address of the local DNS server, if there are any DNS responses that are NOT coming from the DNS server, then those DNS responses might be the spoofed packets coming from the attacker. Are you able to use tcpdump to specifically capture those spoofed DNS packets?  Explain why or why not clearly. If not, how do you detect such attacks that may include additional processing steps? Please specifically describe your attempts.  

## Notes

**Something needs to be noticed in order to successfully run this lab:**
- Task 3: If step 1 (Create zones) did not work with you, you could add the zone entries to /etc/bind/**named.conf.local** file insted of /etc/bind/**named.conf** file.
- Task 5: If the attack is successful at first, it is probably that the request you sent using netwox does not arrive at the user's machine before the local DNS server's packet. You can try to use dig to send more requests on the user machine while running netwox.
- Task 7: To improve the attack success rate, you can modify the final line of the program to only respond to packets from the server: pkt = sniff(filter='udp and dst port 53 and src <your DNS server's address>', prn=spoof_dns).
- Task 8 & 9: If you don't attack successfully, maybe you need to flush the cache and retry the DNS request multiple times.

## Required Files for DNS Setup

**Zone Files for DNS Setup:**
- Zone file for domain example.com: https://seedsecuritylabs.org/Labs_16.04/Networking/DNS_Local/example.com.db
- Zone file for DNS reverse lookup: https://seedsecuritylabs.org/Labs_16.04/Networking/DNS_Local/192.168.0
- Note: If you choose different IP addresses or domain names, you need to modify the above configuration and zone files accordingly.

## Grading (50 points)
Please take screenshots periodically and regularly and include them in your report. They not only serve as evidence of completion but also help the grader understand what you try to achieve. Add adeuqate explaination as needed. See the lab submission example for what it should look like.
* Completeness (35 pts): All the steps as instructed in the lab manual must be included in the report with adequate evidence.
* Presentation (15 pts): The report must be clear and correct in organization and writing with adequate explanation.

