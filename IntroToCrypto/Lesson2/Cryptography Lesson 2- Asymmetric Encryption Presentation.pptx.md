<!-- Slide number: 1 -->
# Asymmetric Encryption
Introduction to Cryptography

### Notes:

<!-- Slide number: 2 -->
# What is asymmetric cryptography?

### Notes:

<!-- Slide number: 3 -->
# Asymmetric Cryptography
While a symmetric cryptographic system has one key that is used for encryption and decryption, asymmetric cryptosystems have two keys: one for encryption and one for decryption.
The encryption key is typically called the Public Key. Everyone knows everyone else’s public key.
The decryption key is called the Private Key. You only know your own private key.

### Notes:

<!-- Slide number: 4 -->
# Example
Imagine that you bought many locks and you set them all so that the same key opened all of the locks. Then you spread those locks all over the world.
Anytime someone wanted to send you something secret, they could put it in a box, lock it with one of your locks and send it to you. You have the only key, so you’d be the only person who could open it and see what was inside.
In this example, the many locks is your public key (widely known), and the one key that can unlock them is your private key (one copy, only you have it).

### Notes:

<!-- Slide number: 5 -->
# Why Do We Need Asymmetric Cryptography
Symmetric cryptosystems require two parties to meet in advance and pre-arrange a shared secret key for the system to work.
This is not always feasible due to time or location constraints.
Asymmetric cryptosystems provide a method for achieving secret communication at a distance without a pre-arranged secret.

### Notes:

<!-- Slide number: 6 -->
# RSA (Rivest-Shamir-Adleman)

### Notes:

<!-- Slide number: 7 -->
# RSA
RSA is the most common asymmetric cryptosystem in use today.
It was published in 1977 by Rivest, Shamir, and Adleman who were working at MIT at the time.
RSA relies on what is called a “one way function”: an operation that is easy to compute, but hard to “undo”. For RSA, the one way function is multiplying two large prime numbers to get one large composite number (this is easy for computers).
The reverse of this would be factoring that large number back into the two original primes, and that is very hard for computers to do.

### Notes:
In fact, the system had been invented 4 years earlier by Cilfford Cocks who was working for British signals intelligence, but his work was classified and no one knew he had invented it until 1997 when the work was declassified. Also, the idea of an asymmetric cryptosystem was first suggested in 1976 by Diffie and Hellman who had worked out a key exchange algorithm based on the same ideas that RSA uses; but Diffie and Hellman never fully developed such a system.

<!-- Slide number: 8 -->
# A Note About Numbers
Throughout this presentation we will refer to what we call “large prime numbers”. You are probably familiar with prime numbers like 13 and 17 and 29; numbers whose only factors are 1 and themselves.
In implementing RSA with a 2048 bit key, the two large prime numbers each have about 300 digits in them. It is difficult to even fathom numbers that large.
In this presentation I will use small numbers as examples to demonstrate ideas, but remember that the computer is doing this with huge numbers.
Also, there is quite a bit of math involved in asymmetric cryptography, and while it is interesting, one does not need to understand all of the math to use the cryptosystem. The computer will do the heavy lifting.

### Notes:

<!-- Slide number: 9 -->
# RSA Setup (Generate a Key Pair)
Step 1: Select two large prime numbers p and q.
Step 2: Multiply p and q to get n.
Step 3: Calculate φ(n)=(p-1)(q-1)
Step 4: Select a positive integer e such that gcd(e,φ(n))=1 (i.e. e and φ(n) are co-prime, share no common factors)
Step 5: Find d such that e*d = 1 (mod φ(n))
Public Key <e,n>
Private Key <d,n>
1) p = 11 and q = 19
2) n = 11 * 19 = 209
3) φ(209)=(10)(18)=180
4) e = 41

5) 101 * 41 = 4141 / 180 = 23 remainder 1
Public Key <41,209>
Private Key <101,209>

### Notes:
Euler’s totient function counts the number of integers less than n that are co-prime to n. Students may not be familiar with the modulus operator.

<!-- Slide number: 10 -->
# Encrypting Information with RSA
RSA is a system for encrypting numbers; if you have a text-based message you want to encrypt, you first need a scheme for converting your text into numbers.
There is a limit to how many bits can be encrypted by RSA (with a 2048 bit key, you can encrypt about 214 bytes of data)
RSA encryption is much more computationally intensive than symmetric encryption (meaning that for a fixed processor speed, symmetric encryption is faster than asymmetric encryption for a fixed size of data to be encrypted)

### Notes:

<!-- Slide number: 11 -->
# RSA Encrypt Example
Recall that your public encryption key (that other people use to send you messages) is <e,n> (<41,209> for our example)
Let’s say someone wants to send you a message m that corresponds to the number 5 in some way (e.g. could be the fifth letter of the alphabet “E”). Here’s how we encrypt:
me mod n = m’	(e.g. 541 mod 209 = 104)
So our encrypted message m’ is 104 in our example. This is what someone sends to us.

### Notes:
Setting up your system so that you individually encrypt each letter of the alphabet and send the encrypted numbers is a very insecure way to use RSA, because you’ve essentially just created a numeric mono-alphabetic cipher where each letter gets enciphered as a certain number every time and it would be subject to all the password cracking techniques we discussed in the previous chapter for mono-alphabetic ciphers.

<!-- Slide number: 12 -->
# RSA Decrypt Example
You receive this encrypted message 104. Recall that your private key (which only you know!) is <d,n> or <101,209> for our example.
You take the encrypted message you received m’ = 104 and decrypt like this:
(m’)d mod n = m	(for our example 104101 mod 209 = 5)
It is important to recognize that only your private key will decrypt this message. The public key does NOT decrypt itself. This is a common misunderstanding for many students.

### Notes:

<!-- Slide number: 13 -->
# How Secure is RSA?
The short answer is: very secure when implemented properly with good key length.
When someone attempts to break RSA encryption, what they need to do is look at the n (or modulus) from your public key and try to factor it back into the original p and q primes.
If p and q were equal, then n = p2 , and so p = √n. Since p and q should be distinct, one must be larger than the other, meaning one is bigger than √n and the other is less than √n.
So step 1 in breaking RSA is taking the square root of n. Then you begin checking the prime numbers less than √n by dividing n by them to see if they divide evenly (if one does, then it is one of the factors).

### Notes:

<!-- Slide number: 14 -->
# How many primes do you need to check?
Mathematicians know that for large values of x, the approximate number of prime numbers less than x is x/ln(x). For us, x = √n so, whatever n is, to break RSA you have approximately √n/ln(√n) primes to check. Here’s a table to give you some idea of what we’re talking about:

| n | 106 | 109 | 1012 | 1020 | 1030 | 1050 | 10100 | 10200 | 10300 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| # of primes | 145 | 3052 | 72382 | 4.3x108 | 2.9x1013 | 1.7x1023 | 8.7x1047 | 4.3x1097 | 2.9x10147 |

### Notes:
Remind students that an RSA 2048 bit key is on the magnitude of 10600! This is why RSA is such a strong encryption method.

<!-- Slide number: 15 -->
# Typical Usage

### Notes:

<!-- Slide number: 16 -->
# Combining Symmetric and Asymmetric Cryptosystems
Because symmetric systems are faster and asymmetric systems can only encrypt a small amount of data, the standard way to use these systems is to combine them.
You use RSA to encrypt a symmetric key and send it to the person you want to communicate with. They can decrypt the message and get the symmetric key. Then when you send them a file that has been symmetrically encrypted they have the key to decrypt it.
So you use asymmetric encryption as a way to share a secret symmetric key without having to meet in advance. This system plays to both systems’ strengths while minimizing their weaknesses.

### Notes:

<!-- Slide number: 17 -->
# Kerckhoff’s Principle

### Notes:

<!-- Slide number: 18 -->
# Kerckhoff’s Principle
Kerckhoff was a dutch cryptographer in the 1800s who said that the strength of a cryptosystem should lie in the strength of the key, not in trying to hide the method.
Up to and during his time, it was common for people to devise “secret” encryption systems, and then they would attempt to keep the method for how their encryption worked secret while using weak keys and trusting the obscurity of the system to protect the information.
Kerckhoff recognized that this was a bad practice, because most of these systems were easily broken, and said that instead, you should publish your system widely, so everyone knows it, but it should still be secure based on the strength of the key.

### Notes:
