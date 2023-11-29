## 4.1 Certificate Authorities and Public Key Infrastructure

### More about Digital Certificates

* Digital Certificates provide:
   * Confidentiality: Contains the Public Key used for encryption
   * Authentication: Signed by Trusted Certificate Authority (CA)

* Remember- Certificates contain the Public Key plus other public information about a server or user

* Certificates must have a corresponding Private Key that only the
server or user should have.

* Certificate Authority: Service that creates and issues certificates
   * Listed as “Issuer” on certificates

* Operating systems (and some Browsers) have a Certificate Store
   * Certificate Manager in Windows
   * Keychain in OSX
   * Firefox has the Mozilla certificate store
   * Includes the “Trusted Root Certificates”

* Many server services will keep certificates and keys on the file system

### How Certificate Authorities Work with TLS

1. **CA** has a **Private/Public Key Pair**

2. **Client(Alice)** has a copy of the CA Public Key in Trusted CA List

3. **Server(Bob)** has it's Certificate Signed by **CA's Private Key**

4. **Client** knows that **Server Certificate** is valid by **checking the signature with CA Public Key**

![image](https://user-images.githubusercontent.com/114191684/234916763-76f7b75b-7eb9-47d7-be04-4c19f472cb18.png)

### Certificate Revocation

How do you know if a certificate has been compromised – should no longer be trusted?

* 2 common methods

* Certificate Revocation List (CRL): The Certificate Authority (CA) publishes a list of the certificates it has revoked.
   * Clients check that website to verify that the cert is still valid
   * Must parse the full list (can be 1000s) to see if the certificate is revoked

* Online Certificate Status Protocol (OCSP)
   * Clients poll a web service for the specific (single) certificate
   * More efficient

### CRL and OCSP

![image](https://user-images.githubusercontent.com/114191684/234914598-d34439a1-b78a-4328-8e62-698af19af75a.png)

### In the Real World...

* Certificate revocation checking can be difficult
   * CRL lists are long files that are hard to keep synched
   * Lots of HTTPS traffic, so checking for all transactions would generate a lot of traffic – even with OCSP
   * OCSP services by CA’s can be unreliable – which could affect browsing if browsers were aggressive at checking OCSP

* OCSP Stapling is the compromise approach and gaining popularity
   * Web server checks its own status with OCSP
   * And then sends it along with its certificate to the client
   * As the OCSP response is signed by the CA, the client can trust it

### OCSP Stapling

![image](https://user-images.githubusercontent.com/114191684/234915446-56a9a24d-aee9-4631-bab1-7c2e1c6c45bd.png)

## Quiz 1

### Quiz 1 Topics

**TCP 3-Way Handshake**

**Web Resources (Static and Dynamic)**

**URL and locating resources**

**Absolute and Relative Paths**

**Parts of an HTTP Message**

**HTTP Message Syntax**

**Request Start Lines and Methods**

**Response Start Lines and Status Codes**

**Request Headers**

**Response Headers**