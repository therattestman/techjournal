## 3.1 GET and POST

### HTTP Message Privacy

* As we have seen in captures, anyone who is able to access a HTTP packet can read the contents

* That means all headers (Response and Request)
* All HTML returned from the site (Responses)

* And... any data sent from the client to the server when completing forms!

### HTML Forms

* A webform, web form or HTML form on a web page allows a user to enter data that is:
   * Processed by a script in the browser (client-side)
   * Or sent to a server for processing (server-side)

* Forms are enclosed in the HTML <fo<span>rm> tag.
   * This tag specifies the communication endpoint to the data entered into the form that should be submitted,
   * and the method of submitting the data, GET or POST

### Sample HTML Form
```
<html>
 <head>
       <title> SEC 260 GET Sample Form</title>
 </head>
 <body>
   Hello SEC 260 Student - Please provide the following for this simple GET form: </br>
        <form action="welcome_get.php" method="get">
           Name: <input type="text" name="name"><br>
           E-mail: <input type="text" name="email"><br>
           <input type="submit">
        </form>
 </body>
</html>
```

### GETs and POSTs

GET: sends form data to the server in the URL
   * Passes them as key/value pairs following in the “Query String” (after the ?)
   * For example:
      
      GET /test/demo_form.asp?first_name=Johnny&last_name=Cyber HTTP/1.1
      
      Host:demo-site.com

POST: sends the data in the body of the request
   * For example:

      POST /test/demo_form.asp HTTP/1.1
      
      Host: demo-site.com

      first_name=johnny&last_name=cyber

 * So – what is the impact of using the different methods?
* GET:
   * GET requests can be cached
   * GET requests remain in the browser history
   * GET requests can be bookmarked
   * GET requests should never be used when dealing with sensitive data
   * GET requests have length restrictions
* POST:
   * POST requests are never cached
   * POST requests do not remain in the browser history
   * POST requests cannot be bookmarked
   * POST requests have no restrictions on data length

### Helpful GET and POST Table

![image](https://user-images.githubusercontent.com/114191684/234897901-333b8003-16e2-48d7-9353-f1ac8d26b6f7.png)

## 3.2 Intro Crypto and HTTPS

### Cryptology Terms

* Cryptology is the study of cryptography and cryptanalysis

* Cryptography: “lock and key” mechanism that protects data through “disguise”

* Cryptographers: folks who create digital locks and keys

* Cryptanalysts: Folks who attempt to remove the “disguise”

* Plaintext: Original + readable text

* Ciphertext: Disguised + scrambled text

* Encrypt: the process of disguising

* Decrypt: Removes disguise

* Cipher: Method which disguises text

* Algorithm: Step-by-step procedure for calculations
   * Think Flow Chart of calculations

* Key: a piece of information that determines the functional output of a cryptographic algorithm or cipher

* Hash function: an algorithm that takes an arbitrary block of data and returns a fixed-size bit string

* Message Digest: Result of a hash function

### Cryptography and Computing

* Acronyms
   * CIA + NR
   * Different A in CIA
      * Confidentiality: Using cryptography to keep data private
      * Integrity: Crypto to ensure that data has not been altered
      * Authentication: Verify that the user is who they claim
      * Non-repudiation: ensure that the user performed the activity (proof that they cannot deny)

### Confidentiality and Crypto

* Use encryption to prevent unauthorized disclosure of data
* Two common applications:
   * Encryption of data in transit
   * Encryption of data at rest
* Two basic methods:
   * Symmetric Encryption (Secret Key)
   * Asymmetric Encryption (Public Key)
* Some processes combine both types

### What is Symmetric Encryption?

* One secret key: (number, word, a random string)
   * Applied to a message to change the content in a particular way
   * Can be as simple as shifting each letter by a number of places in the alphabet. (Caesar Cipher)
   * If the sender and recipient know the secret key, they can encrypt and decrypt messages

* Pros – Fast, simple, and very effective
* Cons – Exchanging keys & keeping keys private!

### What is Asymmetric Encryption?

* Aka: Public Key encryption
* 4 Total Keys
* Uses Two “key pairs”
   * Public key – One key made available to anyone
   * Private key – Another key only the key owner knows

* Any message encrypted using the public key can only be decrypted by the matching private key

* Any message encrypted using the private key can only be decrypted by the matching public key.

* Pros:
   * Do not have to exchange a private or secret key

* Cons:
   * Slower
   * Requires more processing

### Confidentiality - Data in Transit

* Best of both worlds!
   * Modern techniques use asymmetric & symmetric together

   * Use asymmetric to start communication, and then

   * Share a symmetric key to use going forward during the session

* Common uses of this technique:
   * SSL (Secure Socket Layer)- used by HTTPS and other protocols
   * TLS (Transport Layer Security)- new version of SSL
   * SSH (Secure Shell)- common in Linux/Unix

### Asymmetric (Public Key)

* Common issue: How do you share public keys?
   * Store in a directory where they are looked up
   * Or – more commonly, Digital Certificates

### Digital Certificates

* Identifies a user or a server (subject)

* Contains information such as:
   * organization name
   * organization that issued the certificate
   * subject’s e-mail address and country
   * subject's public key

### Encryption in Transit: Putting it Together

* SSL/TLS:
   * Systems exchange public keys (certificates)
   * Use public/private key pairs to establish an encrypted tunnel
   * Create a secret key (symmetric) and send it through the tunnel
   * Use the secret key to send data

### HTTPS - TLS Handshake

![image](https://user-images.githubusercontent.com/114191684/234910581-d9eda75b-f831-44cb-aded-0f739a0a6ddb.png)
