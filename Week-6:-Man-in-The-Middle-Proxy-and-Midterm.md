## 6.1 Man in The Middle Proxy

MITMProxy is a tool that is used to demonstrate MITM attacks, particularly with SSL/TLS.  MITMProxyLinks to an external site. works by intercepting all HTTP and HTTPS requests making the request on behalf of the client, and returning the results.

Since it is able to intercept the HTTPS request, it has the ability to decrypt the communication channel and use its own SSL/TLS method to retrieve the website.  The time after the decryption occurs leaves the data open to an attack, such as simply sniffing the data for sensitive information or even modifying the data in transit.  MITMProxy is able to stop an SSL/TLS connection, allow inspection of the data and then modify it before it passes it on to the intended server.

Commercial Proxies work the exact same way.  This allows the anti-virus and other intrusion detection software to drop malicious traffic before it gets back to the client within an organization.
## 6.2 Midterm

### Midterm Playbook (Setting Up and Configuring a Web Server in HTTPS with a Certificate Authority)

**Web Server:**

1. Setting Up the Web Server:

2. Run dhclient (gets new IP)

3. Ip a to confirm you have an ip

4. Yum install -y httpd (installs Apache/https)

5. Firewall-cmd –permanent –add- port=80/tcp (opens port 80)

6. Firewall-cmd –reload (reloads firewall config)

7. Firewall-cmd –query-port=80/tcp (should report yes)

8. systemctl start httpd (starts httpd)

9. systemctl status httpd (checks status)

10. Curl http://yourip | grep “working properly”

11. Go to the website

**Creating HTML Page:**

1.
```
Cd /var/www/html
Vi index.html
<html>
<head>
<title>
This is the title of my web server
</title>
</head
<body>
Stuff goes here
</body>
</html>
```
2.
:wq (saves document)

**Setting Up the Certificate Authority:**

1. Firewall-cmd –permanent –add- port=22/tcp (opens port 22)

2. cd /etc/pki/CA

3. touch index.txt (used to keep track of certs)

4. echo 1000 > serial (used to assign serial numbers to certs)

5. openssl genrsa -des3 -out private/cakey.pem 2048

6. openssl req -new -x509 -days 365 -key private/cakey.pem -out cacert.pem
Country, state, city : BLANK
Joyce101 as org name org unit name and common name

**Create the cert request on CA (on the web server):**

1. openssl req -newkey rsa:2048 -keyout websrv.key -out websrv.csr 
Same entries as above

2. scp websrv.csr CAIPAddress:/etc/pki/CA

**Sign the cert on the CA:**

1. openssl ca -out websrv.crt -infiles websrv.csr

2. cat websrv.crt

3. scp websrv.crt WebServerIP:/var/www/html

4. ls on that directory to confirm

**Setting up cert and key on the web server:**

1. cp websrv.crt /etc/pki/tls/certs

2. cp websrv.key /etc/pki/tls/private

3. Confirm they are on those directories

4. yum -y install mod_ssl (installs mod-ssl)

5. Firewall-cmd –permanent –add- port=443/tcp (opens port)

6. Firewall-cmd –reload (reloads firewall config)

7. systemctl restart httpd

8. systemctl status httpd

9. Browse to the website
