<!-- Slide number: 1 -->
# Chapter 4: Authentication

### Notes:

<!-- Slide number: 2 -->
# The goal of authentication is to prove that you are who you say you are

### Notes:
This can be challenging over the internet where it is easy for people to pretend to be someone else.

<!-- Slide number: 3 -->
# Types of Authentication

### Notes:

<!-- Slide number: 4 -->
# Something You Know
Passwords
Pin Numbers
Answers to Challenge Questions

![Google Shape;77;p16](GoogleShape77p16.jpg)
Photo by Fakurian Design on Unsplash

### Notes:
The password conundrum: Strong passwords are long and random (hard to guess!), but the human brain has a hard time remembering long random things.

<!-- Slide number: 5 -->
# Something You Have
Phone
Card (Debit/Credit Card, CAC, etc.)
RSA Token

![Google Shape;85;p17](GoogleShape85p17.jpg)
Photo by Paul Hanaoka on Unsplash

### Notes:
CAC- Common Access Card (Standard for US Government employees: military, NSA, DOD, etc.)
RSA Tokens are unique and generate a pseudo-random sequence of digits on a schedule

<!-- Slide number: 6 -->
# Something You Are
Iris or Retina Scans
Fingerprints or Palm prints
Facial ID
Voice ID

### Notes:
Widely used (iPhone used fingerprint, now uses facial recognition)

<!-- Slide number: 7 -->
# Where You Are
Although IP addresses can be spoofed, checking to see what region an IP address is assigned to can be one part of checking someone’s identification.
If a user who usually logs in from Chicago is suddenly logging in from Singapore, then the system should at least raise a red flag.

![Google Shape;99;p19](GoogleShape99p19.jpg)
Photo by Timo Wielink on Unsplash

### Notes:
Often an unusual IP address will trigger an extra layer of authentication like a challenge question or one-time password sent to a verified phone number or e-mail.

<!-- Slide number: 8 -->
# How You Do Something
Scientists have discovered that the patterns of keystrokes you use when you type are as unique as a fingerprint.
This is called Dynamic Keystroke Analysis, and shows great promise as a method for authentication.
Demonstration

### Notes:
Use the link to demonstrate how well the technology can differentiate between users.

<!-- Slide number: 9 -->
# Digital Signatures

### Notes:

<!-- Slide number: 10 -->
# Something Only You Have
One of the major advantages of asymmetric encryption is that it generates 2 separate keys that work as inverses on one another and one key is private while the other is public.
In theory, you are the only person who has access to your private key. This means that if you encrypt something with your private key and send it out on the internet. Anyone can look up your public key and use it to decrypt it and if the decryption works, then the file or message must have been from you, because no one else can generate a file that is decrypted by your public key except you.

### Notes:
This idea is the inverse of asymmetric encryption discussed in chapter 2. This sometimes trips students up. Important to emphasize that by “encrypting” with your private key, you can prove that thing came from you.

<!-- Slide number: 11 -->
# Digital Signature
So, if you want to send a message and prove that it came from you, then you can use your private key to encrypt it and send it.
But remember that asymmetric encryption has size limitations.
So instead of encrypting the message (which doesn’t need to be secret in this scenario), we hash the message, and use our private key to encrypt the hash. The encrypted file containing the hash is our signature. We send the original message along with the signature file.
The recipient uses our public key to decrypt the signature and checks the hash against the hash of the message. If they match, then the message is unaltered and from us (data integrity and source integrity in one step!)

### Notes:
Important to emphasize here that the message itself is not encrypted, so this method is not for secret messages. Digital signatures do not assure confidentiality, but rather data integrity and source integrity.
