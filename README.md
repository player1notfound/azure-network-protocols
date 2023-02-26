<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04



<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.io/4ZOTJxY_d.webp?maxwidth=640&shape=thumb&fidelity=medium" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create two virtual machines, Windows 10 machine and Linux machine, that are on the same Virtual Private Network. Paste the VM-1's public IP address onto Remote Desktop Connection and connect. Install Wireshark and open the software. Filter for ICMP traffic only. To terminate ICMP traffic navigate to Network Security Group in the Linux machine and add an inbound security rule. Deny all ICMP traffic with the priority off port 200. Click the ethernet button followed by the blue button at the top left corner. 
</p>
<br />

<p>
<img src="https://i.imgur.io/VkiRaop_d.webp?maxwidth=640&shape=thumb&fidelity=medium" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter Wireshark to capture Secure Shell Protocol (SSH) packet only in Windows 10 machine. In the Linux machine, command prompt "ssh labuser@10.0.0.5" to which the Wireshark capture Secure Shell Protocol.
</p>
<br />

<p>
<img src="https://i.imgur.io/lQc7FiR_d.webp?maxwidth=640&shape=thumb&fidelity=medium" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter Dynamic Host Configuration Protocol (DHCP) in Wireshark. Type "ipconfig/renew" in command prompt and Wireshark will capture DHCP traffic.
</p>
<br />

<p>
<img src="https://i.imgur.io/Oc62mnf_d.webp?maxwidth=640&shape=thumb&fidelity=medium" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter DNS traffic in Wireshark and initiate DNS trafic by typing in command prompt "nslookup www.google.com." The DNS server generate the IP address of any websites.
</p>
<br />

<p>
<img src="https://i.imgur.io/c3jWxMG_d.webp?maxwidth=640&shape=thumb&fidelity=medium" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter RDP traffic in Wireshark by typing "tcp.port==3389. 
</p>
<br />
