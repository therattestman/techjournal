### VM Configurations:

wks01-James:
MAC Address: 00-50-56-A1-47-56




### Interesting Things to Note:

pfSense:
Before this lab, I had never used pfSense before so I decided to research where it is typically used:
* It is a free and open-source firewall and router
* Provides VPN (Virtual Private Network) functionality for homes, businesses, educational institutions, and government agencies

Tracert:
Before this lab, I hadn't had much experience using Tracert so I wanted to find out the kinds of things that can be done with it:
* Tracert shows the route a packet takes to get to its destination
* Can modify the way it does this using different options such as:
        * -d: specifies to not resolve addresses to hostnames
        * -h _maximum_hops_: specifies the maximum number of hops to search for the target
        * -j _host-list_: specifies loose source route along the host-list
        * -w _timeout_: Waites the number of milliseconds specified to timeout
        * target_host: specifies the name or IP address of the target host
### Lab Deliverables:
Deliverable One:

![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/3baf590b-5e8c-49cf-b3b6-9194035afc40)

Deliverable Two:

![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/2dc20859-67c5-42cc-9f5c-c81bad048dd9)

Deliverable Three:

![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/8f99a5d1-58a1-45bf-897b-9d9c02634e45)

Deliverable 4:

![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/fdfbb346-49d7-4575-8d80-4a312d87cba1)

Difficulties/What I've Learned:
* One of the steps that gave me some trouble was creating the admin account, for some reason the first time I restarted my new name didn’t set. 
* One of the more annoying steps was configuring the IPV4 Properties, I spent easily 20 minutes just trying to find where that window was.
* I’ve also never used pfsense before so there was some difficulty just navigating through the menus trying to find what I need. This is why I personally like command line more.




Sources:

[pfSense Website](https://www.netgate.com/pfsense-plus-software)

[Microsoft Support on Tracert](https://support.microsoft.com/en-gb/topic/how-to-use-tracert-to-troubleshoot-tcp-ip-problems-in-windows-e643d72b-2f4f-cdd6-09a0-fd2989c7ca8e)
