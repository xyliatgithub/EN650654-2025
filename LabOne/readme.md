# Lab 1 - Network Traffic & DoS Attack

In this lab, we will perform an experimental Denial-of-Service attack and collect network packets.

## Setup

Go to http://www.cis.syr.edu/~wedu/seed/lab_env.html to install the pre-built VM image (Ubuntu 16.04 32 bits).

• VM setup instruction (in Virtualbox): http://www.cis.syr.edu/~wedu/seed/Labs_16.04/Documents/SEEDVM_VirtualBoxManual.pdf
• User manual (contains the usernames and passowrds): http://www.cis.syr.edu/~wedu/seed/Documentation/Ubuntu16_04_VM/Ubuntu16_04_VM_Manual.pdf

In this lab, you need to have three VMs under the same local network. Note that these three VMs should be in the promiscuous mode in order to listen to traffics from other VMs. Once you have configured a VM, you can simply clone that VM for two more times to complete the VM setup. Please refer to Appendix A and B of the VM setup instruction.

## Lab Instructions 

1. Please follow the instructions on [this page](https://seedsecuritylabs.org/Labs_16.04/PDF/TCP_Attacks.pdf) to complete the task 1: SYN Flooding Attack of the lab. In case the hyperlink does not work, here's the full URL: [https://seedsecuritylabs.org/Labs_16.04/PDF/TCP_Attacks.pdf]. 
2. You need to fulfill some required additional tasks.

## Lab Instructions 

**Note: A few changes are needed in order to successfully run this lab:**
- Setup: Step 5: Please use the new rspec file "denialOfServiceLevel1_NEW.txt" instead of the file at the given link. You can use the File option or copy the content of "denialOfServiceLevel1_NEW.txt" using the Text Box option.
- Setup: If you follow all the steps but your experiment does not start as expected, please check the error messages. Sometimes you need to try another aggregate since the resources at the selected aggregate are limited.
- Part 5: Step 5: If you are a Mac or Linux user and you cannot use SFTP to connect to the node successfully, you need to use your key like ssh. The command may look like:  
" sftp -i \<the same key with your ssh key\> -o Port=\<Your corresponding port from the previous step\> your_username@host "
- Part7: You could only analyze the regular traffic. Just repeat step1-3 from Part5 four more times. Use iperf to generate traffic and use tcpdump to generate pcap files. You do not need to attack. Notice that you should make each traffic generation time as same as possible.  
To control the time more accurately, You could use the following command:  
"sudo tcpdump -i <interface> -s0 -G <the time you want> -w %H%M_%S.pcap"  
Notice: Do not set the time too long in case the Pcap file will be too large.
- After finishing the lab, please do not forget to delete the resources of your slice so they can be used by other users.
