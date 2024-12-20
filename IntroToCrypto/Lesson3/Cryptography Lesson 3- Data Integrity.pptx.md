<!-- Slide number: 1 -->
# Chapter 3: Data Integrity

### Notes:

<!-- Slide number: 2 -->

Information
Security

### Notes:
The CIA-triad:
1) Confidentiality - only approved people access information (accomplished through cryptography and access controls)
2) Integrity - Information is not tampered with (added to, deleted, or altered); source of the information is verifiable (source integrity vs. data integrity)
3) Availability - Resources are available to approved users when they need them (uptime on servers, databases, etc.)

<!-- Slide number: 3 -->
# Message Digests (Hashes)

### Notes:

<!-- Slide number: 4 -->
# What is a message digest or hash?
A hash is a function that takes data as input, scrambles the data up, and outputs a fixed-length string of bits (usually represented in hexadecimal).
SHA-256 and SHA-512 are common modern hashing algorithms (the numbers at the end indicate the number of bits in the output)
SHA = Secure Hash Algorithm
A hash is like a digital fingerprint

### Notes:
Input data can be a string of characters or a whole file.
Fixed-length output is important.

<!-- Slide number: 5 -->
# Important Features of Hashing Algorithms
Repeatability: Same input always produces the same output
Non-Reversibility: Given a hash, there is no known way to “undo” the hash and say what the original input was
Uniqueness: No two unique inputs will ever produce the same output
Sensitivity: A small change in the input makes a big change in the output
Fixed-Length: The output is always a fixed number of bits in length no matter how big or small the input was

### Notes:

<!-- Slide number: 6 -->
# Examples
Let’s use this SHA-256 hashing tool to test some of these features:
https://xorbin.com/tools/sha256-hash-calculator

### Notes:
Demonstrate to students how changing one small letter generates a totally different hash, how hashing a single letter or a sentence still gives 256 bits of output, and how hashing the same input always generates the same output.

<!-- Slide number: 7 -->
# How Are Hashes Used?

### Notes:

<!-- Slide number: 8 -->
# Crypto-Currency
Crypto-currencies like Bitcoin use something called a “distributed ledger” to keep track of transactions. The ledger is a collection of blocks of data which contain the transaction information. To add a new block to the ledger you have to “chain” it to the previous block by integrating the hash of the previous block in the header of the next block (along with other information). This is called the “block-chain”.
The Bitcoin miner is looking for a nonce to put in the block header that when combined with all the other block information will have a SHA256 hash that starts with a certain number of zeros (more than 20 right now).
This hash is called the “Proof-of-Work” and is very hard to find.

![Google Shape;111;p20](GoogleShape111p20.jpg)
Photo by Dmitry Demidko on Unsplash

### Notes:
Nonce = number used once

<!-- Slide number: 9 -->
# Hash-Based Message Authentication Code (HMAC)
Let’s presume that Alice and Bob have a shared secret symmetric key. Alice wants to send Bob a message. The contents of the message aren’t a secret, but she wants to make sure that no one intercepts the message and alters it en route to Bob.
So Alice generates a hash of the message and uses her shared symmetric secret key with Bob to encrypt the hash. Then she sends Bob the message and the encrypted hash in two separate files. Since Bob has the symmetric key too, he can decrypt the hash and check the hash of the message against what Alice says it is supposed to be. If the hashes match, then the message has not been altered in transport.

### Notes:
This isn’t exactly how HMAC works; HMAC actually uses the symmetric key to generate two new keys (an inner and an outer) and it performs two hashing passes over the data one with the inner key and then a second pass over the output of the first pass along with the outer key. But for beginners, I find the above description in the slides more helpful!

<!-- Slide number: 10 -->
# Digital Signatures
Digital signatures are similar to HMAC, except that they have the ability to verify the identity of the sender (source integrity) as well as verify the integrity of the message itself (data integrity).
Digital signatures use asymmetric encryption instead of symmetric encryption to achieve this double integrity check.
We will cover these in more detail in the next chapter.

### Notes:
Chapter 4 discusses digital signatures in more depth

<!-- Slide number: 11 -->
# Password Hashing
Computers store hashes of passwords not passwords themselves.
Each time you log in, the computer hashes your input and compares the hash to the hash it has stored on file; if they match it lets you in.
If an attacker gains access to your computer, they can’t just steal your password, because they can only see the hash of your password (and hashes are non-reversible…)

![Google Shape;131;p23](GoogleShape131p23.jpg)
Photo by Ariel on Unsplash

### Notes:

<!-- Slide number: 12 -->
# What is a “salted” password hash?
When you set a password, the computer generates a little random string of bits, and it hashes your password together with those bits. The extra random string of bits is called “salt”.
If two users have the same password, they’ll still have different hashes (because they have different salt), so an attacker looking at the hash table won’t know if two users have the same password, and if the attacker does manage to crack one, s/he won’t automatically get the other one.

### Notes:

<!-- Slide number: 13 -->
# Wait a second! I thought you said hashes were non-reversible?!

### Notes:

<!-- Slide number: 14 -->
# Rainbow Tables

| Password | Hash |
| --- | --- |
| Password | e7cf3ef4f17c3999a94f2c6f612e8a888e5b1026878e4e19398b23bd38ec221a |
| ILoveTheUSA | cbd410e2331c036e966eb9a11ba7577ac32616a41ab2f67d3537cd68ea575ce5 |
| Winter2020 | 2d636ebca37bed3ebc4222f751990da32091712ee4947eab98c624ad46ca4985 |
| Spot82 | e7f247075e62325b831b0f4717621e4cb6627c42d980d15e006f03437e86eb4f |

### Notes:
A rainbow table is a table with a list of common passwords and the hash of the password. If an attacker gets access to a a list of password hashes, s/he can search the rainbow table for the hashes they found in the password file and if anyone has a common password, then the hash will match and the attacker will know what the password must be. A fun password cracking website is https://www.crackstation.net.
Another benefit of salting password hashes is that it prevents hackers from using a rainbow table attack. A threat actor can still crack salted password hashes (especially if the password is weak), but they will need a tool like Hashcat or John the Ripper.
