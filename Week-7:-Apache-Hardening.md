## 7.1 Apache

### What is a Web Server?
Based on what we have learned - what is a Web Server?
* A computer system that processes requests via HTTP or HTTPS
* The term can refer to the entire system, or specifically to the software that accepts and supervises the HTTP requests
* Pages delivered are most frequently HTML documents, which may include in addition to text content:
   * images
   * style sheets
   * scripts
* A user agent, a web browser, initiates communication by making a request for a specific resource using HTTP
* The server responds with
   * Content of that resource
   * Or an error message

### Dynamic HTML

* Creating HTML per request (not stored as a static page)
* Scripting languages build the HTML based on conditions (from request, database content, specific user, time of day...)
* Two methods:
   * Server-Side Scripting: The server contains scripts and a script language interpreter to “build” the html, which is then delivered to the client
   * Client-side Scripting: The web page contains a script that the client downloads as part of the web page. The browser executes the script to build the HTML that is displayed.

### Server-Side Scripting

* Used to generate HTML documents dynamically ("on-the-fly") as opposed to returning static documents.
* Primarily used for retrieving and/or modifying information from databases
* Behavior of the website can be scripted in separate files, while the actual web server software remains unchanged.

* Server-side scripting languages:
   * Active Server Pages (ASP)
   * PHP
   * JSP
   * Perl
   * Ruby

### Pros/Cons of Server-Side Scripting

Pros:
* Broader client support. The server sends HTML so the client does not need to support the scripting language

* Minimal execution on the client side can reduce security exposure to client

Cons:
* Web service needs permission to execute scripts on the web server
* Web developers may need elevated permissions of the web server
* Can be more resource intensive on the web server

### Client-Side Scripting

* Client-side scripts are embedded in a website’s HTML markup (HTML files on the server)
* The scripting language must be supported and compatible with the browser
* The browser temporarily downloads that code, and then, apart from the server, processes it to build the final HTML page that is rendered to the server

### Pros/Cons of Client-Side Scripting

Pros:
* Scripts put less stress on the server because they don’t require processing on the server once they’re downloaded
* Developers (and webpages) don’t need to execute permissions on the server

Cons:
* Client needs to process the scripts – may cause resource issues
* Security concerns with potentially malicious scripts
* Server may not have a record of the dynamic web page – which makes transactional activity difficult (follow-up web pages)

### Apache Server-Modules

* Over 20 years old
* Open-source and maintained by the Apache Software Foundation
* Uses a compiled module architecture:
* Extends the core functionality including:
   * server-side programming languages
   * authentication schemes
   * TLS/SSL (mod_ssl)
   * proxy module (mod_proxy)
   * URL rewriting module (mod_rewrite)

### Apache Server: Virtual Host

Virtual Hosting:
* allows one Apache installation to serve many different Web sites.

* For example, one machine with one Apache installation (aka 1 IP address) could simultaneously serve:
   * w<span>ww.example.com
   * w<span>ww.example.org
   * test47.test-server.example.edu

* Uses info in the Client Request Header to point to the correct site

**Overview of 7.1 Lab:**

![image](https://user-images.githubusercontent.com/114191684/234931877-c98d4078-ebed-4dde-99c4-b31e61708818.png)

## 7.2 Apache Hardening

### Confidentiality: Hardening Topics

Web traffic in transit?
* HTTPS

Authentication
* Protect resources by requiring authentication
* Protect authentication credentials using secure technologies

Least Privilege
* Only allow users to access the resources they need
* Prevent exposing unnecessary information about the server/application itself

File System Protections
* Set appropriate permissions on web content, scripts, and configuration files
* Prevent “file inclusion” vulnerabilities

Data Store Protections
* Prevent unauthorized access methods to databases and other backend data stores (e.g. prevent SQL injection)

Server-Side Script Protections
* Prevent script execution when not needed

### Integrity: Hardening Topics

Ensuring data doesn’t change:
* Using certificates and digital signatures
* Preventing Man-in-the-Middle

Prevent File System Changes
* Monitor file-system for unauthorized changes (integrity monitoring)
* Read-only permissions to web content whenever possible

Server-Side Script Protections
* Prevent script execution when not needed

Availability: Hardening Topics

Configuration Settings:
* Protect server/service from resource exhaustion (connection limits, timeouts)

Unload unneeded modules/services
* Simplify the configuration to the minimal required resources
* Reduced complexity can improve the reliability of server/service

### Other Hardening Topics

Updates:
* OS as well as web server and backend applications

Security-Specific Technologies:
* Security modules for the web server (mod_security for Apache)
* OS protection tools (e.g. SELinux)
* Intrusion Prevention systems
* Denial-of-Service Protections
* Web-Application Firewall


