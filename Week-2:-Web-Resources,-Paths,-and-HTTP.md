## 2.1 Web Resources and Paths

### TCP 3-Way Handshake
Sender sends a SYN request to check for connectivity

The receiver sends a SYN-ACK request to confirm connectivity

The original Sender sends an ACK request to end the handshake

### Simple HTTP Connection
In TCP, you need the IP address of the server computer
and the TCP port number associated with the specific
software program running on the server

1. ht<span>tp://207.200.83.29:80/index.html
2. ht<span>tp://www.netscape.com:80/index.html
3. ht<span>tp://www.netscape.com/index.html

The first URL has the machine’s IP address,
“207.200.83.29”, and port number, “80”

The second URL doesn’t have a numeric IP address;
Hostnames can be converted into IP addresses through
Domain Name Service (DNS)

The final URL has no port number. When the port
number is missing from an HTTP URL, the client
assumes the default of 80

### Web Resources

A web resource is the source of web content

Static files on the web server’s file system. These files can
contain anything:
* Text files
* HTML files
* Microsoft Word files
* Adobe Acrobat files, JPEG image files, AVI movie files, or any other format
you can think of

Dynamic content resources can generate content. For
example
* Based on your identity
* Or on the time of day
* Or a live image from a camera
* Or let you trade stocks, search real estate databases, or buy gifts from
online stores

![image](https://user-images.githubusercontent.com/114191684/234724548-a7a85e30-29fd-43d1-b5ca-38e28f2d7f3c.png)

### Identifying and Locating Resources
URIs

Each web server resource has a unique name, so clients
can point out what resources they are interested in

The server resource name is called a uniform resource
identifier, or URI

URIs are like the postal addresses of the Internet,
uniquely identifying and locating information resources
around the world

URIs come in two flavors, called URLs and URNs

### URLs

The uniform resource locator (URL) is the most common form of resource identifier.

URLs describe the specific location of a resource on a particular server.

They tell you exactly how to fetch a resource from a precise, fixed location.

A URL tells precisely where a resource is located and how to access it.

![image](https://user-images.githubusercontent.com/114191684/234725110-d6ed181f-e98e-486c-b80b-50e86e611ce2.png)

### Absolute and Relative Paths

**Relative Paths:**

Relative links only point to a file or a file path

When a user clicks a relative link, the browser takes them to that location on the current site

For that reason, you can only use relative links when linking topages or files within your site,
and you must use absolute links if you're linking to a location on another website.

* index.html
* /graphics/image.png
* /help/articles/how-do-i-set-up-a-webpage.html

**Absolute Paths:**

Absolute paths always include the domain name of the
website, including ht<span>tp://www
* ht<span>tp://www.mysite.com
* ht<span>tp://www.mysite.com/graphics/image.png
* ht<span>tp://www.mysite.com/help/articles/how-do-i-set-up-a-webpage.html

## 2.2 HTTP Methods, Status, and Headers

### HTTP Messages Overview

If HTTP is the Internet’s courier, HTTP messages are the packages it uses to move things around.

Important to understand:
* The three parts of HTTP messages: start line, headers, and entity body
* The differences between request and response messages
* The various functions (methods) that request messages support
* The various status codes that are returned with response messages

### Parts of a HTTP Message

Start Line

Headers

Body

![image](https://user-images.githubusercontent.com/114191684/234730095-32fc9e9e-57ce-4100-b133-00129638b940.png)

The start line and headers are just ASCII text, broken up by lines.

Each line ends with a two-character end-of-line sequence, consisting of a carriage return (ASCII 13) and a line-feed character (ASCII 10)

This end-of-line sequence is written " CRLF.”

The entity-body or message body (or just plain “body”) is simply an optional chunk of
data. Unlike the start line and headers, the body can contain text or binary data or
can be empty.

### HTTP Message Syntax

All HTTP messages fall into two types: request messages and response messages.

Request messages request an action from a web server.

Response messages carry the results of a request back to a client.

Both request and response messages have the same basic message structure

### Start Lines

Start Lines
* All HTTP messages begin with a start line. The start line for a request message says what to do.
The start line for a response message says what happened.

Request line
* Request messages ask servers to do something to a resource.

Response line
* Response messages carry status information and any resulting data from an operation back to a
client.

Methods
* The method begins the start line of requests, telling the server what to do. For example, in the line
“GET /specials/saw-blade.gif HTTP/1.0,” the method is GET.

### Start Lines: Methods
```
Method  Description                                            Message body?

GET     Get a document from the server.                        No
HEAD    Get just the headers for a document from the server.   No
POST    Send data to the server for processing.                Yes
PUT     Store the body of the request on the server.           Yes
TRACE   Trace the message through proxy servers to the server. No
OPTIONS Determine what methods can operate on a server.        No
DELETE  Remove a document from the server.                     No
```

### Response Start Line: Status Codes

Tell the client what happened:
```
Overall range   Defined range    Category

100-199         100-101          Informational
200-299         200-206          Successful
300-399         300-305          Redirection
400-499         400-415          Client error
500-599         500-505          Server error
```

### HTTP Request

Everything after the GET is a Header Field:
```
GET /tutorials/other/top-20-mysql-best-practices/ HTTP/1.1
Host: net.tutsplus.com
User-Agent: Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.1.5) Gecko/20091102
Firefox/3.5.5 (.NET CLR 3.5.30729)
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-us,en;q=0.5
Accept-Encoding: gzip,deflate
Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7
Keep-Alive: 300
Connection: keep-alive
Cookie: PHPSESSID=r2t5uvjq435r4q7ib3vtdjq120
Pragma: no-cache
Cache-Control: no-cache
```

### HTTP Response

Everything after the status is a header

Until DocType which starts the Content
```
HTTP/1.x 200 OK
Date: Sat, 28 Nov 2017 04:36:25 GMT
Server: LiteSpeed
Connection: close
Expires: Sat, 28 Nov 2017 05:36:25 GMT
Cache-Control: max-age=3600, public
Content-Type: text/html; charset=UTF-8
Last-Modified: Sat, 28 Nov 2017 03:50:37 GMT
Content-Encoding: gzip

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Top 20+ MySQL Best Practices - Nettuts+</title>
<!-- ... rest of the html ... -->
```

### HEAD Method

HEAD: Retrieve Header Information
* HEAD is identical to GET, except the server does not return the content in
the HTTP response.
* When you send a HEAD request, it means that you are only interested in the
response code and the HTTP headers, not the document itself.

With this method, the browser can:
* Check if a document has been modified, for caching purposes.
* It can also check if the document exists at all.

Usage: 
* If you have a lot of links on your website, you can periodically send HEAD
requests to all of them to check for broken links.
* This works much faster than using GET.

### Response Headers: Host

Host:
* An HTTP Request is sent to specific IP Addresses
* But since most servers are capable of hosting multiple websites under the
same IP, they must know which domain name the browser is looking for.

### Request Headers: User Agent

User Agent
* This header can carry several pieces of information such as:
   * Browser name and version
   * Operating System name and version.
   * Default language.
* This is how websites can collect certain general information about their
surfers' systems
* For example, they can detect if the surfer is using a cell phone browser and
redirect them to a mobile version of their website

### Request: Other Headers

* Accept-Language: What language the client requests
* Accept-Encoding: Whether the client support g zip compression of HTML

* IF-Modified-Since: If the page is cached on the client
   * It will ask the server if it has been modified since the date
   * If not changed, the server sends a 304 Not-Modified instead of page
* Referer: Tells server what page you are coming from
   * Basically, where did you click the link to this new page
   * Misspelling of referer is correct
* Cookies: More on them later

### Response Headers: Cache-Control

Cache-Control:

A HTTP cache header that contains a set of parameters to define the browser's caching policies in the client requests and server responses

![image](https://user-images.githubusercontent.com/114191684/234734661-9ae4252a-2cf4-4092-b5af-abc88f46a49c.png)


### Response Headers: Content-Type

Content-Type: 

A statement in the response header of the web server which gives the browser information regarding the format of a transmitted file

![image](https://user-images.githubusercontent.com/114191684/234734604-09690518-1880-4456-b26d-a33bc9392809.png)

### Response Headers: Last-Modified

* Last-Modified: Includes the date the page was last modified
* Used in conjunction with the If-Modified-Since Request Header

![image](https://user-images.githubusercontent.com/114191684/234734921-edd021f5-2d4f-495a-a642-011cf56c39b5.png)
