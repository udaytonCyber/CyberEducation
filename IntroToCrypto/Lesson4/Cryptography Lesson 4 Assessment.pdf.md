Cryptography Chapter 4 Assessment

Note to Instructor: These are model questions and are not meant to be exhaustive. Feel free to

copy them into a LMS (e.g., Canvas, Blackboard, or Schoology), a formative assessment tool like

Quizizz or Kahoot, to use them as discussion questions in class, or to add them into a formal

assessment of your own making.

1.  What is Multi-Factor Authentication (MFA) and why is it a good security measure?

2.  Give a personal example of how you have authenticated yourself sometime in the last

couple days.

3.  Give an example of “Something You Have” authentication.

4.  I send you a message with a digital signature and the signature verifies. Why does this

mean that the message must be from me AND must be the message I sent (unaltered)?

5.  In the Zero-Proof Knowledge example from the text where Alice is trying to decide if

Charlie is tricking her or not, imagine that Charlie gets the answer correct 10 times in a

row. What is the probability that Charlie is tricking Alice?

6.  True or False: When you log in to a certain account, they require you to enter a

password and answer a challenge question. This is an example of two factor

authentication.  False

7.  Which of the following are examples of biometric authentication?

a.  Iris Scan ✓

b.  Fingerprint ✓

c.  SmartCard

d.  Facial Recognition ✓

e.  The patterns of how you type a sentence.

8.  When you want to digitally sign something you use:

a.  The recipient’s public key

b.  The recipient’s private key

c.  Your own public key

d.  Your own private key ✓

9.  When you want to verify a digital signature from a sender you use:

a.  The sender’s public key ✓

b.  The sender’s private key

c.  Your own public key

d.  Your own private key

10. True or False: Digitally signing a file encrypts the file itself.  False

Some reasonable answers to the open-ended questions (not meant to be the only right

answers):

1.  MFA is when multiple forms of authentication are combined to give a user access to a

system such as: where you are, what you have, and what you know. The factors must be

from different categories.

2.  Yesterday I went to the bank and showed my driver’s license to the bank teller.

(Answers will vary widely.)

3.  When I get a one-time password sent to my phone, that assumes that I am the person

who has my phone.

4.  You are the only person with your private key, so you are the only person who could

have produced that signature. Also, after decrypting the hash, I see that it matches the

hash of the file I have received, which means that the file is intact and unaltered,

because the hashes would not match if the file had been altered.

5.  If Charlie is tricking Alice by guessing randomly and gets it right 10 times in a row by

pure chance, each guess is .5 probability of guessing correct, so .510 = .0009765 as a

percent this is .09765% which is less than 1 tenth of a percent of a chance. Pretty slim!


