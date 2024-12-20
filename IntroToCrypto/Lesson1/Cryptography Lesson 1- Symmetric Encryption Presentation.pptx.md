<!-- Slide number: 1 -->
# Symmetric Encryption

### Notes:

<!-- Slide number: 2 -->
# What is cryptography?
The word cryptography is a combination of two Greek words: kryptos which means hidden and graphos which means writing.
So cryptography literally means “hidden writing”.
It is the art and science of hiding/disguising a message.

![Google Shape;67;p14](GoogleShape67p14.jpg)

![Google Shape;68;p14](GoogleShape68p14.jpg)

### Notes:

<!-- Slide number: 3 -->
# When did cryptography begin?
In the first century BC, the Roman general Julius Caesar is credited with the first cryptographic cipher, which is named after him: the Caesar Cipher.
To communicate securely across great distances, Caesar would shift the letters of the alphabet in his message.
In this example, the word “bad” would get encrypted as “EDG”. So if anyone intercepted his letters in transit, they looked like gibberish.
What are the weaknesses of this scheme?

![Google Shape;75;p15](GoogleShape75p15.jpg)

### Notes:
Two main weaknesses: 1) Only 25 non-trivial options for shifts; someone could just try them all; 2) the person you’re communicating with needs to know how many letters you’ve shifted the alphabet, so you need to agree upon this in advance.

<!-- Slide number: 4 -->
# Demonstrating the Weakness of Caesar Cipher
You intercept this encrypted message:
HWDUYTLWFUMD NX HTTQ
Let’s use this tool to break the cipher using brute force:
https://cryptii.com/pipes/caesar-cipher

### Notes:
Copy the cipher text into the tool and step through the shifts until the plaintext appears

<!-- Slide number: 5 -->
# What could we do to make a stronger cipher?
The history of cryptography can be considered as a tug-of-war between cryptographers and cryptanalysts:
Cryptographer - someone who encrypts/decrypts data using a cryptographic algorithm
Cryptanalyst - someone who tries to break codes
Once the basic idea of a Caesar cipher was known, breaking them became trivial.
Get into groups and devise a better cryptographic algorithm.

### Notes:
Hopefully students will generalize to the concept of a monoalphabetic cipher.

<!-- Slide number: 6 -->
# Monoalphabetic Substitution Ciphers
One-to-one randomization of letter-for-letter substitution.
Two broad schemes:
1) letters swap (If A → B , then B → A.), or
2) all mixed up (A → D, but D → Q, and Q → M, etc.)
How many different monoalphabetic ciphers are possible? (excluding the trivial case)
Does this seem secure?

### Notes:
25! different monoalphabetic ciphers, which is about 1.6 x 10^25

<!-- Slide number: 7 -->
# ROT 13 Cipher

| A | B | C | D | E | F | G | H | I | J | K | L | M |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ↕ | ↕ | ↕ | ↕ | ↕ | ↕ | ↕ | ↕ | ↕ | ↕ | ↕ | ↕ | ↕ |
| N | O | P | Q | R | S | T | U | V | W | X | Y | Z |

### Notes:

<!-- Slide number: 8 -->
# ROT 13 Cipher Practice
Encrypt: “ohio cyber range”

Decrypt: “PLORE VF NJRFBZR”

### Notes:
“CYBER IS AWESOME”

<!-- Slide number: 9 -->
# How Secure Are Monoalphabetic Ciphers
Lots of different possible combinations.
But once you set the key (the mapping) it never changes.
Think of Cryptograms in the newspaper; people solve them all the time.
In the 800s, an arabic mathematician named Al-Kindi was analyzing the Quran and other texts, and made an observation: certain letters were more common than others.
Every language has a unique letter distribution that holds true for a large enough writing sample.

### Notes:

<!-- Slide number: 10 -->
# English Letter Frequency

![Google Shape;117;p22](GoogleShape117p22.jpg)

### Notes:

<!-- Slide number: 11 -->
# Using Frequency Analysis to Break Ciphers
You must know the language of the cipher (every language has a different frequent letters).
The longer the message the better this works. Short messages may not have the same letter distribution as the larger population.
Analyze the ciphertext for the most frequent letters in the cipher, and then map those to the corresponding common letters in the target language, and use trial and error to fill in the gaps.

### Notes:

<!-- Slide number: 12 -->
# Example Using Frequency Analysis
Oc zrc Fcaflc ah zrc Evwzcx Uzizcu, wv Apxcp za hapq i qapc fcphcsz Evwav, cuzinlwur Beuzwsc, wvuepc xaqcuzws Zpivkewlwzy, fpajwxc hap zrc saqqav xchcvuc, fpaqazc zrc mcvcpil Oclhipc, ivx ucsepc zrc Nlcuuwvmu ah Lwncpzy za aepucljcu ivx aep Fauzcpwzy, xa apxiwv ivx cuzinlwur zrwu Savuzwzezwav hap zrc Evwzcx Uzizcu ah Iqcpwsi.
Use This Website

### Notes:
Preamble to the Constitution enciphered using a monoalphabetic cipher.

<!-- Slide number: 13 -->
# Polyalphabetic Ciphers
The ciphers we have seen so far have consistently mapped one letter or digraph to another letter or digraph, always mapping the same way within a single message.
We have seen how this made the cipher very insecure.
In the 1500s, Giovan Battista Bellaso created the first widely used polyalphabetic cipher, where a repeated plaintext letter didn’t always get mapped to the same ciphertext letter over and over.
Until 1863, when it was broken, it was often called “The Unbreakable Cipher”, or the Vigenere Cipher (after a Frenchman to whom it was erroneously attributed).

### Notes:

<!-- Slide number: 14 -->
# Vigenere Cipher
The Vigenere cipher requires both the sender and receiver to know a secret key, which must be agreed upon in advance.
Symmetric Encryption: When the same key is used to encrypt and decrypt the message.
The secret key is written above the message letter for letter, repeated as necessary.
Using a Vigenere Square (on the next slide), the letter from the keyword tells you what column to use and the plaintext letter tells you what row to use. Their intersection is the ciphertext letter.

### Notes:

<!-- Slide number: 15 -->
# Vigenere Square

![Google Shape;147;p27](GoogleShape147p27.jpg)

### Notes:

<!-- Slide number: 16 -->
# Vigenere Example

| T | H | I | S | I | S | A | K | E | Y | T | H | I | S | I | S | A | K | E | Y |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| j | a | c | k | i | s | t | h | e | m | o | l | e | r | u | i | n | h | i | m |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

### Notes:

<!-- Slide number: 17 -->
# Practice Vigenere Cipher
Find a partner. Agree on a common keyword or keyphrase
Each person writes a unique secret message and enciphers it using the key.
Read the ciphertext to your partner.
Use the key to decrypt your partners ciphertext.

### Notes:

<!-- Slide number: 18 -->
# Is the Vigenere Cipher Secure?
For short messages, the Vigenere square is very secure.
If the length of the key is the same as the length of the message, the Vigenere is nearly unbreakable. It becomes equivalent to a “one-time pad”.
Keys that use a variety of letters are more secure than keys that use many repeated letters (Compare: EXCEED vs. TRAINS).
If the key length is short and the message is long (i.e. the key is repeated many times in enciphering the plaintext), then this cipher is susceptible to a sophisticated frequency analysis attack.

### Notes:

<!-- Slide number: 19 -->
# ENIGMA Machine
Leading up to WWII, the Germans developed a polyalphabetic electronic enciphering machine called ENIGMA.
It used reels that had 26 electronic leads on each side of the reel, and internal wiring scrambled electrical signals coming in and out of the reels.
An operator set the reels in a specific order, then started typing the plaintext message. Each time the operator pressed a key, one of the reels advanced one letter, so that each letter was being scrambled with a different key setting.
If it had been used properly, the ENIGMA machine would provide near perfect secrecy for communications.

### Notes:

<!-- Slide number: 20 -->

![This Enigma machine is of the type used by the German Navy on submarines to encode messages during World War II. This short video explains how it works.

Find out more on the National Museums Scotland website: http://www.nms.ac.uk/explore

Connect with us:
Blog http://blog.nms.ac.uk/
Twitter https://twitter.com/NtlMuseumsScot
Facebook https://www.facebook.com/NationalMuseumsScotland
Instagram https://instagram.com/nationalmuseumsscotland/
Pinterest https://uk.pinterest.com/NtlMuseumsScot/](GoogleShape176p32.jpg)

### Notes:

<!-- Slide number: 21 -->

![Google Shape;181;p33](GoogleShape181p33.jpg)

### Notes:

<!-- Slide number: 22 -->
# Modern Symmetric Encryption

### Notes:

<!-- Slide number: 23 -->
# Symmetric Encryption
Definition: A cipher is symmetric when the same key that encrypts the message is also used to decrypt the message.
Modern symmetric encryption algorithms are computer-based and operate on binary data (bits grouped into bytes).
Modern symmetric encryption is fast, can handle large amount of data, and is very secure (when implemented properly)
Disadvantage: Both parties must have the same secret key to communicate (this is not a huge stumbling block as you’ll see later)

### Notes:

<!-- Slide number: 24 -->
# Advanced Encryption Standard (AES)
AES-128 (using keys of length 128, 192, or 256 bits) is the current symmetric encryption standard from the United States National Institute of Standards and Technology (NIST) since 2001; it was officially adopted by the US government as a standard in 2002.
AES is the only publicly available encryption algorithm ever approved by the US National Security Agency (NSA) for encrypting top secret level information.
AES-128 is a block cipher: it operates on 128 bit blocks of data; 128 bits is 16 bytes, and the bytes are arranged into a 4x4 matrix for transformation

### Notes:

<!-- Slide number: 25 -->
# Overview of AES
AES uses the key the user provides (128, 192, or 256 bits) to generate a unique key for each “round” of encryption.
The first round key is XORed together with the first 128 bit matrix (often called a “state matrix”)
Then the following steps occur for each round:
Substitution of bytes according to a pre-defined table
Rows are shifted
Columns are mixed using matrix multiplication
Next round key is XORed together with the resulting matrix

### Notes:
The number of rounds varies depending on the size of the key (128 bit = 10 rounds ; 192 bit = 12 rounds ; 256 bit = 14 rounds); in the last round the column mixing step is skipped.
