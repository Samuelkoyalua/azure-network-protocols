<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Install Wireshark
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/lxv12kO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


  <p>
<img src="https://i.imgur.com/fgAHXtj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Let's start by setting up a resource group, which acts like a container for all our resources, making them easier to manage. Once that's in place, we'll create two virtual machines.

The first virtual machine will run on Windows 10, providing a familiar environment for various tasks and applications. It's great for users who are comfortable with Windows and need its specific capabilities.

The second virtual machine will be based on Ubuntu Linux, known for its stability and versatility. It's a solid choice for a wide range of purposes, from development to running server applications.

With these two virtual machines, we're covering different needs and preferences, ensuring flexibility and efficiency in our setup.</p>
<br />

<p>
<img src="https://i.imgur.com/xnSdxiK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


  <img src="https://i.imgur.com/vQqvM8o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After setting up our virtual machines, the next step is to establish a remote desktop connection to VM1 using its public IP address. This allows us to access VM1's desktop environment from a remote location, giving us full control over its operations.

Once connected to VM1, we'll proceed with installing Wireshark. Wireshark is a powerful network protocol analyzer that helps us inspect the data traffic on our network. By installing Wireshark on VM1, we gain the ability to monitor and analyze network activity directly from within the VM's environment.</p>
<br />

<p>
<img src="https://i.imgur.com/BQ0T82k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Let's fire up Wireshark and initiate packet capturing by clicking on the shark icon. This action begins capturing live packets, allowing us to monitor network traffic in real-time. Next, we'll filter the captured packets to focus solely on ICMP (Internet Control Message Protocol) traffic. To do this, we'll simply type "icmp" into the filter bar and hit enter. This filters out all packets except those related to ICMP, which can be particularly useful for troubleshooting network connectivity and diagnosing issues.








<p>
<img src="https://i.imgur.com/a1RBAVI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Next open powershell and ping vm2's private ip address while on vm1


</p>
<br />






<p>
<img src="https://i.imgur.com/uoNi0hy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>



Next We're going to block ping requests from reaching VM1 by configuring VM2's network security group to block ICMP traffic. After observing that we'll allow ICMP again.





