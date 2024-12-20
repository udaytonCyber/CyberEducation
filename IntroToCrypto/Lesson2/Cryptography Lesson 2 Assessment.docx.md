

**Cryptography Chapter 2 Assessment**

**Note to Instructor:** These are model questions and are not meant to be exhaustive. Feel free to copy them into a LMS (e.g., Canvas, Blackboard, or Schoology), a formative assessment tool like Quizizz or Kahoot, to use them as discussion questions in class, or to add them into a formal assessment of your own making.

1. In broad terms, contrast symmetric and asymmetric cryptography.
2. In your own words, what is a “one-way function”?
3. What are the two main disadvantages of asymmetric cryptography?
4. How does combining symmetric and asymmetric cryptography mitigate the disadvantages of both systems?
5. Why is asymmetric cryptography helpful?
6. Which of the following are considered secure key sizes for RSA?
   1. 256 bits
   2. 1024 bits
   3. 1536 bits
   4. 2048 bits **✓**
   5. 3072 bits **✓**
   6. 4096 bits **✓**
7. About how large are the prime numbers that are multiplied together to get the “n” value in RSA 2048 in base 10?
   1. Smaller than 1 billion
   2. About 50 digits long
   3. About 100 digits long
   4. About 200 digits long
   5. About 300 digits long **✓**
8. True or False: Kerckhoff’s principle says that as long as you keep your cryptographic system secret, then your ciphers will be secure. **False**
9. You want to send John an encrypted message. Which of the following is correct?
   1. Encrypt the message with your private key.
   2. Encrypt the message with your public key.
   3. Encrypt the message with John’s private key.
   4. Encrypt the message with John’s public key. **✓**
10. You receive an encrypted message from Sue. Which of the following should you do?
    1. Decrypt the message with your private key. **✓**
    2. Decrypt the message with your public key.
    3. Decrypt the message with Sue’s private key.
    4. Decrypt the message with Sue’s public key.

Some reasonable answers to the open-ended questions (not meant to be the only right answers):

1. Symmetric encryption has one secret key that is shared by both parties, and it is used to both encrypt and decrypt, whereas asymmetric encryption has two keys (one public and one private) that act as inverses of each other, so to send you a message, I encrypt using your public key, and then only you can decrypt the message using your public key.
2. A one-way function is a mathematical operation that is easy to perform in one direction, but hard to do in the opposite direction. For humans, this would be like differentiation vs. integration; most people find it easy to differentiate a function, but hard to integrate one (unless it is an easy one). In this example, neither is hard for the computer.
3. The two main disadvantages of asymmetric cryptography are that it is slower than symmetric cryptography and that it has a very small limit on the size of information that can be encrypted.
4. You can overcome these disadvantages by using asymmetric encryption to encrypt your symmetric key and send it to the recipient, then you and the recipient can communicate using symmetric encryption, but your symmetric key is safe because it was encrypted while it was being transmitted. In other words, you use asymmetric encryption as a lock to protect your symmetric key while it is in transit.
5. Asymmetric encryption is helpful precisely because it allows you to securely communicate with someone far away without first pre-arranging a shared secret key.

