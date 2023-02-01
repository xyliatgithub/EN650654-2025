# Lab 1 - Local DNS Attack

In this lab assignment, you will need to setup multiple SEED lab VMs and perform an DNS attack. In addition to those tasks required by the SEED lab documentation, you also need to finish the additional tasks described below.

## Setup 

Go to  http://www.cis.syr.edu/~wedu/seed/lab_env.html to install the pre-built VM image (Ubuntu 16.04 32 bits).  

•	VM setup instruction (in Virtualbox): https://seedsecuritylabs.org/Labs_16.04/Documents/SEEDVM_VirtualBoxManual.pdf  
•	User manual (contains the usernames and passowrds): https://seedsecuritylabs.org/Labs_16.04/Documents/SEEDVM_VirtualBoxManual.pdf  

In this lab, you need to have **three VMs** under the same local network. Note that these three VMs should be in the promiscuous mode in order to listen to traffics from other VMs. 
Once you have configured a VM, you can simply clone that VM for two more times to complete the VM setup.   

## Instructions

1. Please follow the instructions in the DNS_Local PDF file to complete all the 9 tasks. The first three tasks are basically the environment and DNS setup.   
•	Note: You will not be able to complete all the tasks without proper setup. If you encounter any problem, please reach out to the CA for help ASAP. 

2. Please complete the following **additional tasks**:  
•	In **Task 5 - Directly Spoofing Response to User**, use tcpdump on the "User" machine to capture all the DNS packets.  
•	Since you know the IP address of the local DNS server, if there are any DNS responses that are NOT coming from the DNS server, then those DNS responses might be the spoofed packets coming from the attacker. Are you able to use tcpdump to specifically capture those spoofed DNS packets?  Explain why or why not clearly. If not, how do you detect such attacks that may include additional processing steps? Please specifically describe your attempts.  

## Notes

**Something needs to be noticed in order to successfully run this lab:**
- Task 5: If the attack is successful at first, it is probably that the request you sent using netwox does not arrive at the user's machine before the local DNS server's packet. You can try to use dig to send more requests on the user machine while running netwox.
- Task 7: To improve the attack success rate, you can modify the final line of the program to only respond to packets from the server: pkt = sniff(filter='udp and dst port 53 and src <your DNS server's address>', prn=spoof_dns).
- Task 8 & 9: If you don't attack successfully, maybe you need to flush the cache and retry the DNS request multiple times.

## Required Files for DNS Setup

**Zone Files for DNS Setup:**
- Zone file for domain example.com: https://seedsecuritylabs.org/Labs_16.04/Networking/DNS_Local/example.com.db
- Zone file for DNS reverse lookup: https://seedsecuritylabs.org/Labs_16.04/Networking/DNS_Local/192.168.0
- Note: If you choose different IP addresses or domain names, you need to modify the above configuration and zone files accordingly.

