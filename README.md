<h1>Troubleshooting SSH connections and web GUI connections</h1>

<h2>Description</h2>
Several times while building this router I have been locked out of the routers web GUI and unable to connect to the WAP or SSH into it. In the quick little troubleshooting write up I will show you how to connect to your RaspAP web GUI and SSH. We will be doing this by plugging our Raspberry Pi into our computer that has an established internet connection and sharing that connection with the Raspberry Pi.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Control Panel Network Manager</b>

<h2>Environments Used </h2>

- <b>Windows 11</b> (21H2)

<h2>Program walk-through:</h2>

- Make sure your laptop is connected to an established internet connection<br/>
- Plug the Raspberry Pi into your Ethernet port on your laptop<br/>
<p align="center">
Launch the utility Control Panel and Select "Network and Internet"<br/>
<img src="https://i.imgur.com/Tkv6Lik.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select "Change adapter settings"  <br/>
<img src="https://i.imgur.com/VhPM3XJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right-click your internet connection. For me it was my WiFi adapter <br/>
<img src="https://i.imgur.com/YTQvJ0O.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select Properties:  <br/>
<img src="https://i.imgur.com/BaA1zk4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the properties configure the ethernet port you want to share your internet connection on. Just copy my configuration below.<br/>
<img src="https://i.imgur.com/uuRPe7u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
- After you have done this there will be a internet connection flowing into your ethernet port which is plugged into your Raspberry Pi which will give it internet access<br />
- The next step to connecting back to your RaspAP Web GUI or SSH is to find the exact IP address of the raspberry pi connected over your ethernet connection<br />
<br />
Go into command line and input "ipconfig". Look for the ip address of the ethernet to ethernet connection. This is the IP address asigned to your ethernet port, not the IP address of the Raspberry Pi <br/>
<img src="https://i.imgur.com/W87WwQP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To find the IP address of the Raspberry Pi you will run the "arp -a" command which will detect all nodes over a connection. In this screenshot you can see that the very first IP address in the table has a unique physical address. This is the MAC address of Rasberry Pi computers  <br/>
<img src="https://i.imgur.com/4bNSoVt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We are going to put this IP address  192.168.137.137 into our web browser because it is the IP address of the Raspberry Pi. We will connect to the RaspAP web GUI service over the ethernet connection until we fix the configurations and have a stable WAP<br/>
<img src="https://i.imgur.com/0Jk0JOs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
- We can also connect to the Raspberry Pi through SSH (if its enabled) with this IP address. We can also make the configurations over the SSH terminal connection if we would like<br />
<br />
SSH into the Raspberry Pi for more configuration options and more advanced troubleshooting<br/>
<img src="https://i.imgur.com/zHfMGkk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
