## 1.1 Introduction to the Web

### Who invented the "web" and when? And for what purpose?
The World Wide Web was invented by Tim Berners-Lee in 1989 while working at CERN
(European Council for Nuclear Research). It was originally intended to automate
information sharing between scientists across different Universities and Institutes
around the world.

### What's a HTML: What it is, its history, and importance
HTML (HyperText Markup Language) is a standard markup language for web page
creation. With it, you are able to create and structure sections, paragraphs, and links.
The first version of HTML was created in 1993 by Tim Berners-Lee. There have been
many versions of HTML since but the most prevalent one in the 2000s was HTML 4.01
which was made a standard in December 1999.

### What is a URI: How are they used on the modern web?
A URI (Uniform Resource Identifier) is a sequence of characters that identifies a logical
or physical resource and distinguishes one resource from another. These are usually
connected to the internet. The most common kind of URI is a URL (Uniform Resource
Locator), also known as a web address, which is used for identifying and locating
websites and other web-connected resources.

### What is HTTP: At a high level- describe how it works
HTTP (HyperText Transfer Protocol) is the popular language for all web applications. It
is also a “multimedia courier”. HTTP uses reliable data transmission protocols to make
sure items like jpegs and text are not scrambled or damaged in transit

## 1.2 HTML and VI

### What is a Web Page?
* Static Web pages are text files containing HTML
* HTML (Hyper Text Markup Language)
    * Describes the structure and formatting of a website
* HTML markup includes special "elements" such as head, title, body, header, footer, article, section, p, div, span, img, and many others.
*  To use these elements in HTML they should be formatted as <*insert element here*>

### Basic HTML Format

Every element that is opened needs to be closed such as ```<html> </html>```
```
<html> (opening tag for document)
<head> (section not displayed but contains info for browser)```
<title> (The name of the page that is printed in the tab title)```
Title goes here
</title> (closing tag – means the section is done)
</head>
<body> (body contains what is displayed in the browser)
Webpage stuff goes here!
</body>
</html>
```

### Simple Tags

Hyperlink Tags:
```
<a href="http://www.telerik.com/" 
title="Telerik">Link to Telerik Webtitle="Telerik">
Link to Telerik Website</a>site</
```
Image Tags:
```
<img src="logo.gif" alt="logo" />
```
Text formatting tags:
```
This text is <em>emphasized.</em>
<br />new line<br /><br />new line<br />
This one is <strong>moreThis one is <strong>more
emphasized.</strong>emphasized.</strong>
```

### Using VI
* Unix-Based text Editor
* Default editor on many Unix/Linux installs
* Has Two Different Modes
   * INSERT: type 'i' and you can edit the file using arrow keys to navigate through
   * COMMAND: Hit ESC key and then ":" to enter commands
      * :w writes file
      * :wq writes and quits file
      * :q! quits without saving
      * :q quits if no changes were made