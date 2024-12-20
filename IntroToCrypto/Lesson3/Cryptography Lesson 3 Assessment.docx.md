

**Cryptography Chapter 3 Assessment**

**Note to Instructor:** These are model questions and are not meant to be exhaustive. Feel free to copy them into a LMS (e.g., Canvas, Blackboard, or Schoology), a formative assessment tool like Quizizz or Kahoot, to use them as discussion questions in class, or to add them into a formal assessment of your own making.

1. Why is it important that hashing algorithms are non-reversible?
2. Describe a hashing “collision” in your own words.
3. Sam wants to create a hashing algorithm and decides to set it up so that when you run the algorithm, it uses the current date/time stamp from the computer to scramble the input data into a fixed-length output. What aspect of hashing algorithms does this idea violate?
4. In your own words, describe why it is important to store passwords as hashes with salt. Be sure to address why salting the hashes is important.
5. When using an HMAC, why is it important to encrypt the hash of the message file?
6. True or False: Hashing a file is the same as encrypting it. **False**
7. How many hexadecimal characters does the SHA-512 hashing algorithm output?
   1. 32
   2. 64
   3. 128 **✓**
   4. 256
   5. 512
8. When you use a message digest to verify that a file has not been tampered with, which of the following aspect(s) of cybersecurity are you addressing:
   1. Confidentiality
   2. Integrity **✓**
   3. Availability
   4. People
   5. Policies
9. Which of the following is a type of attack used to crack password hashes?
   1. Replay Attack
   2. Man-In-The-Middle Attack
   3. DDoS Attack
   4. Rainbow Table Attack **✓**
   5. Blue Team Attack
10. True or False: The “salt” for your password hash is only generated when you set a password. **True**

Some reasonable answers to the open-ended questions (not meant to be the only right answers):

1. If a hashing algorithm were reversible, then someone could use a program to “undo” a hash and see the input that was used to generate the hash. This would make cracking hashed passwords very easy.
2. A collision occurs when a hashing algorithm produces the same hash for two different inputs.
3. By using the time/date stamp as part of the scrambling function, the algorithm will scramble input differently every time it is run. So, if you hash “password” and get hash1 as your output, then five minutes later you run “password” through the algorithm again, you’ll get a different hash, because the time/date stamp is different. This violates the repeatability aspect of hashing algorithms.
4. Storing passwords as hashes is important so that if an attacker gains access to your password file, they won’t have user passwords right away. They’ll have to try to crack the password hashes to get the passwords which will at least slow them down. Salting those hashes is important because it further slows the attacker down and if two users have the same password, they won’t have the same hashes.
5. If you don’t encrypt the hash of the message file, then an attacker could intercept the file and the hash, change the file, and then rehash the altered file and send on the altered file with the updated hash and the message would verify. By encrypting the hash, you prevent an attacker from altering the hash, which in turn means they can’t alter the message (because then it wouldn’t hash to the correct value).

