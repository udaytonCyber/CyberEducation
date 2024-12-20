Cryptography Chapter 1 Assessment

Note to Instructor: These are model questions and are not meant to be exhaustive. Feel free to
copy them into a LMS (e.g., Canvas, Blackboard, or Schoology), a formative assessment tool like
Quizizz or Kahoot, to use them as discussion questions in class, or to add them into a formal
assessment of your own making.

1.  Define symmetric encryption.

2.  Give an example of a BAD keyword for a Vigenère cipher and explain why it is bad.

3.  Why is the Caesar cipher not secure?

4.  Explain one way that a generic alphabetic substitution cipher can be broken.

5.  Describe the concept of reversibility and why it is important in cryptography.

6.  Which of the following are valid key lengths for AES?

a.  64 bits
b.  128 bits ✓
c.  160 bits
d.  192 bits ✓
e.  256 bits ✓

7.  AES operates on blocks of data; what size blocks does AES operate on?

a.  16 bits
b.  32 bits
c.  64 bits
d.  128 bits ✓
e.  256 bits

8.  How large is the key space for a Caesar cipher?

a.  5 keys
b.  15 keys
c.  18 keys
d.  25 keys ✓
e.  32 keys

9.  True or False: In a poly-alphabetic cipher, a specific plaintext letter will always encipher

as one specific ciphertext letter (e.g., “p” always enciphers as “X”).  False

10. Which of the following are components of the ENIGMA machine?

a.  Plugboard ✓
b.  Radio Transmitter
c.  Lightboard ✓
d.  Rotors ✓
e.  Monitor

Some reasonable answers to the open-ended questions (not meant to be the only right
answers):

1)  Symmetric encryption algorithms use the same key for encryption and decryption.

2)  The keyword ABRACADABRA is a bad keyword for a Vigenère cipher because it only uses
5 unique letters, the letter A (which maps letters to themselves) is repeated many times,
and there are repetitions within the keyword itself (“ABRA”) which could create patterns
in the ciphertext.

3)  The Caesar cipher is not secure because it only has a keyspace of 25 keys which is easy

to brute force using modern technology.

4)  (Option 1) Pattern recognition/analysis: looking for patterns like a three-letter word

that is repeated often (probably “the”) or a ciphertext letter that occurs twice in a row
(often “ee” or “oo”); (Option 2) Frequency analysis: creating a frequency table for the
letters in the ciphertext and comparing them to a frequency table for the target
language of the message and making educated guesses about which letters substitute
for which other letters.

5)  Reversibility is the idea that whatever steps an algorithm uses to encrypt a message

need to be reversible so that someone who has the ciphertext and key can reverse the
encryption and get the original message back. Reversibility implies a 1-to-1 relationship
between a plaintext letter in a certain position/order and its corresponding ciphertext.


