

**Introduction to Cryptography**

**Lab 4: RSA Authentication**

**Description:**

The purpose of this lab is to get practical experience digitally signing documents and verifying digital signatures.

OpenSSL is an open-source toolkit that contains a variety of cryptography related functions. You can read more about this toolkit by visiting their website <https://www.openssl.org>. On their website, you can also find the manual pages describing how to use the toolkit. In this lab we’ll be using the following commands (with linked manual pages for review):

* [General OpenSSL Commands Manual Page](https://www.openssl.org/docs/manmaster/man1/)
* [OpenSSL dgst Manual Page](https://www.openssl.org/docs/manmaster/man1/openssl-dgst.html) (openssl dgst is the sub command we’ll use to generate and verify digital signature files)

**Objectives:**

1. Use the RSA private key you generated in Lab 2 to digitally sign the short text file you generated in Lab 1. Then verify your own signature for practice.
2. Given several documents, a digital signature, and a public key, figure out which document is the authentic one.

**Materials:**

This lab was developed as part of a module to be used with the Ohio Cyber Range (OCR). In that context, your teacher should have given you instructions for how to access a virtual Linux machine through the OCR. However, this lab can be done on any Linux machine.

**Instructions**

**Step 1:** Log in to your VM as “**student**” using the password **Pa$$w0rd** (that is a zero after the “w”).

**Step 2:** In the top left corner there is an “Applications” menu; hover over “System Tools” and select “Terminal”.

**Step 3:** Use your RSA private key from Lab 2 to digitally sign your message.txt file from Lab 1.

* Type **ls -l** and press [Enter].
  + You should see a file called **message.txt** and another file called **namersakey.pem**.
* Type **openssl dgst -sha256 -sign namersakey.pem -out namemessage.txt.sha256 namemessage.txt** and press [Enter].
  + “**openssl dgst**” is accessing the dgst or digest sub-command of OpenSSL; we’ll discuss this more in a later chapter
  + “**-sha256**” is specifying which digest algorithm to use
  + “**-sign namersakey.pem**” is indicating that we want to digitally sign this document with our private key
  + “**-out namemessage.txt.sha256**” is indicating that the signature should be written to the file message.txt.sha256
  + “**namemessage.txt**” is indicating what file to sign
* Type **cat namemessage.txt.sha256** and press [Enter].

You should see gibberish, because this is the hash of the **namemessage.txt** file encrypted using your RSA private key.

**Step 4:** Verify your signature

Normally you would verify the signature of someone else who sent you a file, but we’re practicing here with a file that you yourself signed.

* Type **openssl dgst -sha256 -verify namepubkey.pem -signature namemessage.txt.sha256 namemessage.txt** and press [Enter].
  + “**openssl dgst**” accesses the digest sub-command for OpenSSL.
  + “**-sha256**” indicates the hashing algorithm that was used.
  + “**-verify namepubkey.pem**” indicates that you want to verify a signature using **namersapubkey.pem** as the public key to verify with.
  + “**-signature namemessage.txt.sha256**” indicates the file with the signature.
  + “**namemessage.txt**” indicates the file that was signed.

You should get a “**Verified OK**” message telling you that the hash of the file matches the decrypted file signature. This means that the file is actually from the person who it claims to be from and that the file has not been tampered with.

**Step 5:** Concept Check

* Type **cd lab4** and press [Enter].
  + “**cd**” is a command used to change directory
* Type **ls -l** and press [Enter].

You should see the following files: **invoice1.txt, invoice2.txt, invoice3.txt, invoice4.txt, invoice.txt.sha256, alicepubkey.pem**.

You have Alice’s public key, and a digital signature for an invoice from Alice, but your inbox had four separate copies of the invoice from Alice, and you don’t know which one is the real invoice. Use what you know about digital signatures to find the real invoice from Alice.

**Step 6:** Submit your work to your teacher.

Submit your **namepubkey.pem** and **namemessage.txt.sha256** files to your teacher.


