### Linux Commands:
* kill

   * Kill is a command that is used to terminate processes manually
   * Syntax:  kill -s signal|-p -- pid
   * Example: kill -9 1234
* fdisk

   * fdisk is a command that creates and manipulates partition tables
   * Syntax: fdisk -egvy -i|-u -b blocks -c cylinders -h heads -s sectors -f mbrfile -l blocks disk
   * Example: sudo fdisk -l /dev/sda
* wget

   * wget is a command that retrieves content from web servers | name means "web get"
   * Syntax: wget -c|--continue -s|--spider -q|--quiet -O|--output-document file --header 'header: value' -Y|--proxy on/off -P DIR -U|--user-agent agent url

### Lab Deliverables
Deliverable 1.  Login as the named user (not root!) and attempt to ping google.com, ad01 and fw01.  Provide a screenshot similar to the one below that shows the three successful pings.
![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/ac881345-dd5e-4de2-8d70-d08b0618a485)

Deliverable 2.  Using WKS01, Provide a screenshot showing the successful ping using dhcp01's hostname only (leave off yourname.local).
![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/e6cabc07-96c0-4121-9b0b-9e9ef6dc16c2)

Deliverable 3.  Provide a screenshot that shows a successful ssh session as your named Linux user from wks01:
![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/f1ae27bd-6b0f-42c3-ab12-b30c731506b9)

Deliverable 4:  Provide the first 10 commands recorded in your history file:
![image](https://github.com/JNicholls2026/James-Nicholls-Tech-Journal/assets/114191684/77acfec7-1504-4949-a14c-b65e806b198f)

Deliverable 5.  This is a two part question:

a. What security implications does this file represent?  List at least one pro and one con.  
b. What command is used to clear bash history?

Con: If a user gets a hold of this file, they can get an admin’s username and password.

Pro: Commands get saved so they can be used again in the future.
