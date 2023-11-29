## 5.1 Hashes and Digital Certs

### Integrity- Hash Function

* Algorithm that computes a fixed-bit-length string from a block of data
   * “Message” is the data
   * “Message Digest” is the fixed-bit string
      * Often called “hash”
* MD5 – creates 128-bit message digest
   * Popular but has weaknesses
* SHA-1: Creates 160 bit
* SHA-2: 256 and 512 bit

### Integrity - File Hash

* Can verify data or files by recording the hash of original

* Re-calculate hash after transfer

* If they match, the file was not altered

* If they don’t, the file was corrupted or changed

### Crypto Goals

* Confidentiality: Using cryptography to keep data private
   * Encryption in Transit
   * Encryption at Rest
* Integrity: Crypto to ensure that data has not been altered
* Authentication: Verify that the user is who they claim
* Non-repudiation: ensure that the user performed the activity (proof that they cannot deny)

### Non-Repudiation

* Repudiate means to deny – so
* Non-repudiation:
   * Assurance that someone cannot deny something.
   * The ability to ensure that a party cannot deny the sending of a message that they originated.

* In computing – “Digital Signatures” are used
   * Use both Digital Certificates and Hashes

### Non-Repudiation-Digital Signature Basics

* Alice sends a note to Bob
* To digitally sign
   * Alice “hashes” the note (e.g. creates a 160-bit SHA-1 hash)
   * Alice then encrypts the hash with her private key
   * Alice then sends the not with the encrypted hash attached
* To Verify
   * Bob receives a note
   * Bob uses Alice’s public key to decrypt hash
   * Calculates hash of note
      * If hashes match -> then proof Alice sent it!

## 5.2 Decrypting TLS

Transport Layer Security (TLS) encrypts data sent over the Internet to ensure that eavesdroppers and hackers are unable to see what you transmit which is particularly useful for private and sensitive information such as passwords, credit card numbers, and personal correspondence

If Wireshark knows the session key of a TLS session (the symmetric that gets created) it can decode encrypted TLS packets.

Systems can store these keys in a log file if the SSLKEYLOGFILE environmental variable is set.  Some browsers (Chrome and Firefox) will look for this variable and store the keys there.