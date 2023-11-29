## 8.1 + 8.2 Mod Security

### Apache and Modules

* Remember – Apache uses Modules to provide configuration options and specialized services to the web server

* For example: when we configured TLS (HTTPS), we used mod_ssl

* Modules are loaded based on included statements in the httpd.conf file
* Modules have their own config files to set parameters (e.g. ssl.conf)

### Mod_Security

* Open Source – Web Application Firewall

* Basically – monitors web requests and responses looking for malicious patterns

* Uses regular expressions to match those patterns

* Can block requests or responses if the pattern is found

* ModSecurity is a web application layer firewall.
   * It is free software released under the Apache license

* It is a set of rules with regular expressions that helps to instantly ex-filtrate the commonly known exploits.

* ModSecurity obstructs the processing of invalid data (code injection attacks)

* To detect threats, the ModSecurity engine scans all the requests and relative responses

* If the HTTP request is valid it is, then passed to the website content.

* Invalid requests are blocked

### Mod_Security - Configuration

Relatively easy to set up:
1. Install Mod_Security module (yum, apt-get...)

2. Ensure the module is loaded

3. Download the security rules you want to use
   * Basic rules are called the Core RuleSet (or CRS)

4. Tune as needed for your application
   * Enable/disable certain rules
   * Create custom rules

### Mod_Security: Core Rules

In order to provide protection to generic web applications, the Core Rules use the following techniques:

* HTTP Protection – detects violations of the HTTP protocol and a locally defined usage policy

* Real-time Blacklist Lookups – utilizes 3rd Party IP Reputation

* Web-based Malware Detection – identifies malicious web content by checking against the Google Safe Browsing API.

* HTTP Denial of Service Protections – defends against HTTP Flooding and Slow HTTP DoS Attacks.

* Common Web Attacks Protection – detects common web application attacks

Techniques:

* Automation Detection – Detects bots, crawlers, scanners, and other recognizable malicious activity

* Integration with AV Scanning for File Uploads – detects malicious files uploaded through the web application.

* Tracking Sensitive Data – Tracks Credit Card usage and blocks leakages.

* Trojan Protection – Detects access to Trojan horses.

* Identification of Application Defects – alerts on application misconfigurations.

* Error Detection and Hiding – Disguises error messages sent by the server.

### Introducing Basic Web Attacks: Directory Traversal

Directory traversal aims to access files and directories that are stored outside the web root folder.

Attackers could access arbitrary files stored on the file system including application source code and/or critical system files

* By manipulating URLs with “dot-dot-slash (../)” sequences and its variations
   * `http://some_site.com.br/../../../../etc/shadow`
   * Cookie: TEMPLATE=../../../../../../../../../etc/passwd
* Using absolute file paths
   * http://some_site.com.br/get-files?file=/etc/passwd
   * http://testsite.com/get.cgi?f=/var/www/html/admin/get.inc

### Directory Traversal: Percent Encoding

Percent-encoding is a mechanism to encode 8-bit characters that have specific meaning in the context of URLs.
* It is sometimes called URL encoding.
* The encoding consists of substitution: A '%' followed by the hexadecimal representation of the ASCII value of the replace character
* Special characters needing encoding are:
':', '/', '?', '#', '[', ']', '@', '!', '$', '&', "'", '(', ')', '*', '+', ',', ';', '=', as well as '%' itself.

### Directory Traversal Encoding

Request variations
* Encoding and double encoding:
* %2e%2e%2f represents ../
* %2e%2e/ represents ../
* ..%2f represents ../
* %2e%2e%5c represents ..\
* %2e%2e\ represents ..\
* ..%5c represents ..\
* %252e%252e%255c represents ..\
* ..%255c represents ..\

### Directory Traversal and Mod_Security

* Found in the ”Tight-Control” rules file

### Mod_Evasive

* Apache Module to help protect the server against Denial-of-Service events

* Can block IPs that are maliciously attacking servers to tie up resources

* Can block IPs that may accidentally connecting and tying up resources

* mod_evasive can report malicious activity via email and syslog.
* The mod_evasive module works by creating an internal dynamic hash table of IP addresses and URIs
* And denies any single IP address for any of the following conditions:
   * Requesting the same page more than a few times per second
   
   * Making more than 50 concurrent requests on the same child per second
   
   * Making any requests while temporarily blacklisted (on a blocking list)