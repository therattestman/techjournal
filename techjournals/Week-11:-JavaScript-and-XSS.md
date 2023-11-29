## 11.1 JavaScript Info and XSS

### What is JavaScript?

* Browsers have limited functionality
   * Text, images, tables, frames
* JavaScript allows for interactivity
* Initially Developed as a Client-Side scripting language
   * Create Dynamic Web Content in the Browser
* Browser/page manipulation
   * Reacting to user actions
* A type of programming language
   * Easy to learn
   * Developed by Netscape
   * Now a standard exists –
     
     w<spam>ww.ecma-international.org/publications/standards/ECMA-262.HTM

### Java and JavaScript

* Netscape Mozilla working with Sun (creators of Java) in the 1990’s

* They were developing a web-scripting language to be embedded in HTML and executed by the browser – originally called LiveScript

* Changed name to JavaScript to foster the Sun partnership.

* They share some common syntax and approaches but very different languages

### JavaScript Allows Interactivity

* Improve appearance
   * Especially graphics
   * Visual feedback

* Site navigation

* Perform calculations

* Validation of input

### How Does It Work?

* Embedded within HTML page
   * View source

* Executes on client
   * Fast, no connection needed once loaded

* Simple programming statements combined with HTML tags

* Interpreted (not compiled)
   * No special tools are required

### JavaScript Statements


### Basic Javascript Example
```
<html>
<head><title>My Page</title></head>
<body>
<script language="JavaScript">
document.write('This is my first →
JavaScript Page');
</script>
</body>
</html>
```
### Mouseover Example
```
<html>
<head><title>My Page</title></head>
<body>
<p>
<a href="myfile.html">My Page</a>
<br />
<a href="myfile.html"
onMouseover="window.alert('Hello');">
My Page</A>
</p>
</body>
</html>
```
### Form Example
```
<script language="JavaScript">
window.prompt('Enter your name:','');
</script>
<form>
<input type="button" Value="Press"
onClick="window.alert('Hello');">
</form>
```

### JavaScript window.alert Method

**Alert Box**
* An alert box is often used if you want to make sure information comes through to the user.
* When an alert box pops up, the user will have to click "OK" to proceed.

**Syntax**
window.alert(‘sometext’);
* The window.alert() method can be written without the window prefix.
  
  alert(‘I am an alert box!’);

### onerror Event

Execute a JavaScript if an error occurs when loading an image:

<i<span>mg src="image.gif" onerror="myFunction()">

So – useful in XSS...

If you reference an image file that does not exist, it will run the error function/method

<i<span>mg src=“NoFile.gif” onerror=alert(‘VulnerableToXSS’)>

## 11.2 XXX, XSRF, and Path Traversal