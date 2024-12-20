

**Introduction to Cryptography**

**Lab 3: Message Digests and Hash-Based Message Authentication Codes (HMAC)**

**Description:**

The purpose of this lab is to practice generating and verifying digests and hash-based message authentication codes (HMAC).

OpenSSL is an open-source toolkit that contains a variety of cryptography related functions. You can read more about this toolkit by visiting their website <https://www.openssl.org>. On their website, you can also find the manual pages describing how to use the toolkit.

In this lab we’ll be using the following commands (with linked manual pages for review):

* [General OpenSSL Commands Manual Page](https://www.openssl.org/docs/manmaster/man1/)
* [OpenSSL dgst Manual Page](https://www.openssl.org/docs/manmaster/man1/openssl-dgst.html) (**openssl dgst** is the command we’ll use to generate message digests and HMAC)

**Objectives:**

1. Generate a message digest for a file.
2. Generate a HMAC for a file.
3. Given a file and a HMAC, validate whether the file is intact or not.

**Materials:**

This lab was developed as part of a module to be used with the Ohio Cyber Range (OCR). In that context, your teacher should have given you instructions for how to access a virtual Linux machine through the OCR. However, this lab can be done on any Linux machine.

**Instructions**

**Note:** Where you see “**name**” you should use your own name. So, in step 4 instead of **namesymkey.bin** I would use **doughertysymkey.bin**.

**Step 1:** Log in to your VM as “**student**” using the password **Pa$$w0rd** (that is a zero after the “w”).

**Step 2:** In the top left corner there is an “Applications” menu; hover over “System Tools” and select “Terminal”.

**Step 3:** Generate a message digest for a file.

* Type **ls -l** and press [Enter].
  + You should see your text file from Lab 1 **namemessage.txt**
    - This is the file we’ll make a digest for.
* Type **openssl dgst -sha256 -out namemessage.txt.dig namemessage.txt** and press [Enter].
  + “**openssl dgst**” accesses the digest subcommand for OpenSSL.
  + “**-sha256**” indicates what hashing algorithm to use (SHA-256 is the default, so we could have omitted this).
  + “**-out namemessage.txt.dig**” tells the computer to write the digest/hash to the **message.txt.dig** file.
  + “**namemessage.txt**” tells the computer what file to use as input for the digest algorithm.
* Type **cat namemessage.txt.dig** and press [Enter].
  + You should see a string of 64 hexadecimal characters.

**Step 4:** Generate an HMAC for the message.txt file.

* Type **openssl dgst -sha256 -mac hmac -macopt hexkey:$(cat namesymkey.bin) -out namemessage.mac namemessage.txt** and press [Enter].
  + “**openssl dgst**” is accessing the digest sub-command for OpenSSL.
  + “**-sha256**” is indicating the hashing algorithm to be used.
  + “**-mac hmac**” is indicating that we want a hash-based message authentication code.
  + “**-macopt hexkey:$(cat namesymkey.bin)**” is indicating that we want to read in the key for
  + “**-out namemessage.mac**” is telling the computer to write the HMAC to the **message.mac** file.
  + “**namemessage.txt**” is telling the computer what file to generate an HMAC for.

You could then send your **message.txt** file along with the **message.mac** file, and as long as the recipient has the same symmetric key as you, they could run the same command on **message.txt** and check their HMAC-SHA256 result against yours to verify that the file is complete and un-altered.

Notice that we did NOT encrypt the message file. It is still readable as plaintext. Also note that the HMAC and the digest that we calculated are not the same.

**Step 5:** Concept Check

* Type **cd lab3** and press [Enter].

This command moves you into the “integrity” subdirectory.

* Type **ls -l** and press [Enter].

You should see a symmetric key file, five secret messages, and a file containing the HMAC for the real secret file.

* One of the five secret files is unaltered; the other four have been tampered with. Use what you have learned about HMACs to find the unaltered file.

**Step 6:** Submit Your Work

E-mail your teacher the namemessage.mac file you created in step 3.

**Note:** There is an “**-hmac**” option for “**openssl dgst**”, however OpenSSL takes the **string** text you put immediately following the **-hmac** option, turns it into hexadecimal and uses that as the hex key.

If you and your partner agreed to use a keyword for hmac instead of a keyfile you could do something like this:

**openssl dgst -sha256 -hmac Keyword message.txt**

Since the string “Keyword” in hexadecimal is 4b6579776f7264, the following should generate the same HMAC:

**openssl dgst -sha256 -mac hmac -macopt hexkey:4b6579776f7264 message.txt**

**Extra Resources:**

[A Useful Blog Post about HMACs](http://nwsmith.blogspot.com/2012/07/using-openssl-to-generate-hmac-using.html)

[Wikipedia Link to HMAC Entry](https://en.wikipedia.org/wiki/HMAC)


