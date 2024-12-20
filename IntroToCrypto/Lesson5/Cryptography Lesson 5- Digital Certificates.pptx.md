<!-- Slide number: 1 -->
# Chapter 5: Digital Certificates

### Notes:

<!-- Slide number: 2 -->
# Creating Trust Online

### Notes:

<!-- Slide number: 3 -->
# When you go to your bank’s website, how do you know it is really your bank?

### Notes:
By the nature of the internet, it is difficult to know exactly who is “on the other end of the line” so to speak. Who is really hosting that website? Who is this person I’m chatting with or e-mailing? The early internet was mainly used for communication and sharing information. Getting “catfished” when you’re sharing quilting patterns on an internet forum may be embarrassing, but there are no real negative consequences. But as the banking and commercial applications of the internet became more widely used, it became important to have a way to establish trust online. We needed a way for official organizations and people in the physical world to identify their true identities online.

<!-- Slide number: 4 -->
# How do you create trust when no one can see each other?

### Notes:
It turns out that humans have solved this sort of problem before. When you go to the bank and hand the bank teller a pile of cash to deposit in your bank account, you don’t personally know or trust the bank teller. But you trust the bank, and by hiring and training and employing the teller, the bank is implicitly vouching for the teller, saying “You can trust this person.” And because we trust the bank, we trust the person the bank trusts. Of course there are also sensible precautions like receipts, deposit slips, double counts, cameras, etc. So we use something called a “trusted third party” to establish trust between ourselves and an unknown entity (like a bank teller). This is how it is done online as well.

<!-- Slide number: 5 -->
# Certificate Authorities

### Notes:

<!-- Slide number: 6 -->
# What Is a Certificate Authority (CA)?
A company that verifies a person or company’s identity in the physical world, and issues a digital file (called a “certificate”) for the company to use online to prove they are who they say they are.
Two Types:
Root CAs: Top of the chain; self-signed certificate; typically off-line
Intermediate CAs: Certificates signed by the root CA or other intermediate CA; these are the CAs that actually issue certificates to applicants.

### Notes:
CAs are the “trust third parties” of the internet; they are reputable companies that we all trust to verify the physical identity of an online entity and then issue a credential to bind the physical identity to the online identity. The idea of a distributed hierarchy of CAs is very important.

<!-- Slide number: 7 -->
Root Certificate
Authority
Intermediate Certificate Authority
Intermediate Certificate Authority
Digital Certificate A
Digital Certificate B
Digital Certificate C
Digital Certificate D

### Notes:
There is often more than one “level” of intermediate CA after the root before you get to a CA that is issuing certificates. Two main benefits of a distributed CA hierarchy: 1) Avoids a bottleneck; if there were only a couple CAs and everyone had to go through them, their turn-around times for certificates would be slow; and 2) If a CA is compromised by a threat actor then all of the intermediate CAs beneath it and all the certificates they have issued are compromised; by creating lots of intermediate CAs that issue certificates if one gets compromised it only affects a small portion of the certificates (which can be reissued by a non-compromised CA).

<!-- Slide number: 8 -->
# Contents of a Digital Certificate
Distinguished Name (DN) of the certificate owner and certificate issuer
Serial number for the certificate (a unique identifier assigned by the CA)
The public key of the certificate owner
Date the certificate was issued
Date the certificate expires
Digital signature of the CA that is issuing the certificate

### Notes:
A distinguished name is a unique name that only the applicant can use; typically this would be the legal name of the company or person applying for the certificate. Go to a secure website on your web browser and show students what the digital certificate looks like.

<!-- Slide number: 9 -->
# Life Cycle of a Certificate

### Notes:

<!-- Slide number: 10 -->

### Notes:
Certificates are typically valid for one year from the date of issuance.

<!-- Slide number: 11 -->
# Types of Digital Certificates
SSL Certificates
Domain Validated (DV)
Organization Validated (OV)
Extended Validation (EV)
Code Signing Certificates
Client Certificates

### Notes:
SSL Certificates are most common; used to secure internet traffic between web browser and web server. The different levels of validation refer to how deeply the CA verifies the applicants real identity. DV only validates that the applicant has the legal right to use the domain on the certificate (like facebook.com); OV validates information about the organization as well; EV is the most in depth verification process.
Code signing certificates allow software companies to digitally sign their software, updates, and patches so that users can be confident that the software/update they have is actually from the company and not a malicious actor posing as the company, and that the files have not been tampered with.
Client certificates are for individuals, and act like digital ID cards to verify that an online entity is who they claim to be in the physical world.
