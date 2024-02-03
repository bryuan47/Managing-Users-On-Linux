# Managing-Users-On-Linux
<p align="center">
<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/eef4ea4b-7492-4ee6-9925-e11f9854c74c"
/>
</p>

<h1>Managing Users on Linux with the Linux Ubuntu Command Line</h1>
</br>In this tutorial, we go through the basics of managing users on a system such as creating new users and resetting passwords! <br />



<h2>Environments and Technologies Used</h2>

- Various Command-Line Tools

<h2>Operating Systems Used </h2>

- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Analyzing current users on a system
- Creating Users
- Deleting Users
- Creating Passwords for Users
- Observe Users Password Details
- Creating Password Expiration for Users
- Creating Expiration Date for User accounts
- Lab Cleanup!

<h2>Actions and Observations</h2>


<p>
<img src="![Linux](https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/1a711d16-10f7-4431-ac8b-97dd497e4b2b)"
/>
</p>
<p>
1) Through the Azure Portal create two virtual machines one with Windows 10 OS and the other with Linux(Ubuntu) OS. Creating virtual machines automatically creates the virtual network and subnet. When the machines have started log into the Windows VM and download Wireshark to observe packet traffic. 
</p>
<br />

<p>
<img src="https://github.com/bryuan47/azure-network-protocols/assets/76184628/53595e23-22b9-473e-9469-7909688ec470"
>
</p>
<p>
2) After installing Wireshark on the Windows VM open it and filter for "ICMP" traffic in the search bar. Without pinging the second VM nothing will appear in the results so the next step will be to open Windows Powershell and ping the private address from the Ubuntu VM. (Retrieve the Private IP Address through Azure Portal) 
  Return back to Wireshark and observe the packet traffic after pinging the IP address in Powershell. 
  Another interesting thing you can do is go into your Network Security Groups in your Ubuntu VM disable inbound ICMP traffic and see how the traffic in Wireshark will cease upon this. Reenable when finished observing.
</p>
<br />


<p>
3) After observing SSH traffic filter for SSH traffic next in the search bar. Head back into Powershell on the Windows machine and SSH into your Ubuntu Linux machine by typing "ssh (username) (private IP address)" into the command line. Then return to Wireshark to observe the traffic. Type "exit" to stop the ssh connection to the Ubuntu machine. 
</p>

<p> 
4) To observe for DHCP traffic enter DHCP in the above filter box instead of SSH. Go back to your Windows command line and type "ipconfig /renew" to issue a new address to your machine. Go back to Wireshark and observe the traffic. 
</p>

<p>
5) After observing DHCP traffic replace DHCP in the filter box with "DNS". Then return to your command line type "nslookup" and use an example domain such as "google.com" to see the IP address for the website. Then return to Wireshark and observe the traffic. 
</p>

<p>
6) This might be the easiest one! Examing for RDP means going back to Wireshark and replacing the filter box with "RDP" for traffic. Then immediately you can see the traffic is constant. This is because you are using Remote Desktop to access to machine in the first place!
</p>

<p>
7) Don't forget to cleanup! You don't want to leave any virtual machines running to avoid unnecessary costs!
</p>
<br />
