Cryptography Chapter 5 Assessment

Note to Instructor: These are model questions and are not meant to be exhaustive. Feel free to

copy them into a LMS (e.g., Canvas, Blackboard, or Schoology), a formative assessment tool like

Quizizz or Kahoot, to use them as discussion questions in class, or to add them into a formal

assessment of your own making.

1.  In your own words, explain the need that certificate authorities satisfy on the internet.

2.  Describe the four “life” stages for a digital certificate.

3.  What distinguishes DV, OV, and EV SSL certificates? (i.e., What is the difference between

each?)

4.  In your own words, explain why code-signing certificates are important.

5.  Give at least two reasons why a certificate authority should have a distributed hierarchy

structure with multiple intermediate CAs under its root CA.

6.  True or False: Digital certificates are issued by big name companies like Amazon and

Facebook.  False

7.  A root certificate is signed by...

a.  a CA from another company.

b.  itself. ✓

c.  one of its intermediate CAs.

d.  no one; root certificates are not signed.

8.  A typical SSL certificate will contain which of the following (mark all that apply):

a.  A distinguished name ✓

b.  An expiration date ✓

c.  The private key of the certificate owner

d.  The public key of the certificate owner ✓

e.  The digital signature of the certificate owner

9.  True or False: Anyone can get a digital certificate.  True

10. Which of the following will occur many times over the life of a certificate?

a.  Enrollment
b.  Distribution
c.  Validation ✓
d.  Expiration
e.  Revocation

Some reasonable answers to the open-ended questions (not meant to be the only right
answers):

1)  When we interact with online entities through the internet, we don’t really know who
we are dealing with on the other end “of the line” (so to speak). Certificate authorities
are trusted third parties who establish the identity of a company/person and issue them
a digital certificate to bind their identity to that digital certificate. This enables us to
trust websites for sensitive tasks like banking, health care, and commerce.

2)  The life cycle of a certificate begins with enrollment, when an entity creates a CSR and
sends it to a CA asking for a certificate. When the CA verifies the entity and generates a
signed certificate and sends it to the entity, this is distribution. Validation occurs
anytime someone checks to see if the certificate is valid. The certificate will then expire
on its expiration date, unless there is a reason to revoke it before then, in which case it
will be added to a certificate revocation list (CRL).

3)  The main difference between DV, OV, and EV SSL certificates is how much the online

entity has to prove before they are validated by the certificate authority; DV only needs
to prove a right to use the named domain; OV must also prove some basic facts about
the organization requesting the certificate; EV must pass an even more stringent
validation.

4)  Code-signing certificates allow trust companies to sign their software, updates, and

patches so that users know the code is actually from the designated company and that it
hasn’t been tampered with.

5)  One reason why a distributed CA hierarchy is good is because it prevents a certificate

“bottleneck” with lots of entities requesting certificates from just a few CAs who would
be overloaded which would make the wait-time for a certificate inconvenient. A second
reason is because if a CA is compromised, then all of the certificates it has issued are
compromised. If there are multiple intermediate CAs and one gets compromised, the
other CAs can keep functioning, and only the certificates issued by the one intermediate
CA need to be revoked.


