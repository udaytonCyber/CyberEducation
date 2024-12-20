

**Introduction to Cryptography**

**Lab 1: Generating and Using AES Encryption Keys**

**Description:**

The purpose of this lab is to practice generating a key-file, to see what the contents of the key-file look like, and to use the key to encrypt and decrypt a simple message. You’ll be using OpenSSL in a Linux BASH terminal to execute the commands below.

OpenSSL is an open-source toolkit that contains a variety of cryptography related functions. You can read more about this toolkit by visiting their website <https://www.openssl.org>.

On their website, you can also find the manual pages describing how to use the toolkit. In this lab we’ll be using the following commands (with linked manual pages for review):

* [General OpenSSL Commands Manual Page](https://www.openssl.org/docs/manmaster/man1/)
* [OpenSSL enc Manual Page](https://www.openssl.org/docs/manmaster/man1/enc.html) (**openssl enc** is the command we’ll use to encrypt and decrypt in this lab)
* [OpenSSL rand Manual Page](https://www.openssl.org/docs/manmaster/man1/rand.html) (**openssl rand** is the command we’ll use to generate a random symmetric encryption key in this lab)

**Objectives:**

1. Generate a private key-file of length n bits
2. Use AES to encrypt a file
3. Use AES to decrypt a file

**Materials:**

This lab was developed as part of a module to be used with the Ohio Cyber Range (OCR). In that context, your teacher should have given you instructions for how to access a virtual Linux machine through the OCR. However, this lab can be done on any Linux machine.

**Instructions**

**Note:** Where you see “name” you should use your own name. So, in step 3 I would give my file the name **doughertysymkey.bin**.

**Step 1:** Log in to your VM as “student” using the password **Pa$$w0rd** (that is a zero after the “w”).

**Step 2:** In the top left corner, there is an “Applications” menu; hover over “System Tools” and select “Terminal”.

**Step 3:** Generate a random 128-bit key (each hex character represents 4 bits, so a string of 32 hex characters is equivalent to 128-bits).

* Type **openssl rand -out namesymkey.bin -hex 32** and press [Enter]
  + “-hex 32” tells the computer to generate 32 random hexadecimal characters (0-9 and A-F)
  + “-out namesymkey.bin” tells the computer to output those 32 random hexadecimal characters in a file named namesymkey.bin

Linux doesn’t use extensions to read files, so you can put any extension you want on any file (or no extension). The **.bin** extension here is simply used to tell the user that this file contains binary data.

* Type **ls** and press [Enter] to see your file.
  + “ls” is a command used in Linux to “list” the contents of your working directory
* Type **cat namesymkey.bin** and press [Enter] to see the contents of your key.
  + “**cat**” is a command used in Linux to combine files or strings or to view the contents of a file

**Step 4:** Create a text file.

* Type **touch namemessage.txt** and press [Enter]
  + “**touch**” is a command used to create a file.
* Type **date >> namemessage.txt** and press [Enter]
  + “**date**” is a command to generate the current time/date stamp.
  + “**>>**” is an operator that tells the computer to append something onto a file.
* Type **echo “name AES Encryption” >> namemessage.txt** and press [Enter]
  + “**echo**” will output whatever text you have in quotes, and this command is appending that text to your file.
* Type **cat namemessage.txt** and press [Enter] to view the contents of your text file.

**Step 5:** Use your key to encrypt your file.

* Type **openssl enc -aes-128-cbc -in namemessage.txt -out namemessage.txt.enc -pass file:./namesymkey.bin** and press [Enter]
  + “**openssl enc**” uses the encrypt function built into the OpenSSL toolkit, the default is to encrypt data.
  + “**-aes-128-cbc**” is identifying the encryption algorithm you want to use, here: 128-bit AES with Cipher Block Chaining (CBC) (a variation of AES).
  + “**-in namemessage.txt**” is what you want to encrypt.
  + “**-out namemessage.txt.enc**” will output the encrypted data to the named file.
  + “**-pass file:./namesymkey.bin**” will use the symmetric key file you generated earlier as the encryption key.
* Type **cat namemessage.txt.enc** and press [Enter] to view the contents of the encrypted message file.

**Note:** You should see gibberish here!

**Step 6:** Decrypt your file.

* Type **openssl enc -d -aes-128-cbc -in namemessage.txt.enc -out decryptedmessage.txt -pass file:./namesymkey.bin** and press [Enter]
  + “openssl enc” uses the encrypt function built into the OpenSSL toolkit.
  + “-d” tells the computer you want to decrypt instead of encrypt.
  + “-aes-128-cbc” is designating the encryption algorithm as above.
  + “-in namemessage.txt.enc” is telling the computer what file you want to decrypt.
  + “-out decryptedmessage.txt” tells the computer what file to write the decrypted data to.
  + “-pass file:./namesymkey.bin” tells the computer what key to use to decrypt.
* Type **cat decryptedmessage.txt** and press [Enter] to view the contents of your message.

**Step 7:** Submit your work.

Submit your 128-bit key file and your encrypted message file to your teacher according to their instructions.


