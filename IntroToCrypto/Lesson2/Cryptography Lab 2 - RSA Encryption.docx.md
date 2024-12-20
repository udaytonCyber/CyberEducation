

**Introduction to Cryptography**

**Lab 2: RSA Encryption**

**Description:**

The purpose of this lab is to generate an RSA public/private key pair and use them to encrypt your AES symmetric key and then decrypt that key. You’ll be using openssl in a Linux BASH terminal to execute the commands below.

OpenSSL is an open-source toolkit that contains a variety of cryptography related functions. You can read more about this toolkit by visiting their website <https://www.openssl.org>. On their website, you can also find the manual pages describing how to use the toolkit.

In this lab we’ll be using the following commands (with linked manual pages for review):

* [General OpenSSL Commands Manual Page](https://www.openssl.org/docs/manmaster/man1/)
* [OpenSSL genrsa Manual Page](https://www.openssl.org/docs/manmaster/man1/openssl-genrsa.html) (**openssl genrsa** is the command we’ll use to generate our RSA key pair)
* [OpenSSL rsa Manual Page](https://www.openssl.org/docs/manmaster/man1/openssl-rsa.html) (**openssl rsa** is the command we’ll use to export our public key file, in general this subcommand is used to manage RSA keys)
* [OpenSSL rsautl Manual Page](https://www.openssl.org/docs/manmaster/man1/openssl-rsautl.html) (**openssl rsautl** is the command we’ll use to encrypt/decrypt RSA, this is a general RSA utility)

**Objectives:**

1. Use openssl to generate an RSA public/private key pair
2. Use RSA to encrypt a file
3. Use RSA to decrypt a file

**Materials:**

This lab was developed as part of a module to be used with the Ohio Cyber Range (OCR). In that context, your teacher should have given you instructions for how to access a virtual Linux machine through the OCR. However, this lab can be done on any Linux machine.

**Instructions**

**Note:** Where you see “**name**” you should use your own name. So, in step 3 I would give my file the name **doughertyrsakey.pem**.

**Step 1:** Log in to your VM as “student” using the password **Pa$$w0rd** (that is a zero after the “w”).

**Step 2:** In the top left corner there is an “Applications” menu; hover over “System Tools” and select “Terminal”.

**Step 3:** Generate an RSA 2048 key pair using openssl (note: the public and private keys are stored in the same file here).

* Type **openssl genrsa -out namersakey.pem 2048** and press [Enter].
  + “**openssl genrsa**” is a command used to generate rsa keys.
  + “**-out namersakey.pem 2048**” tells the computer to generate a 2048 bit key and output it to the file **namersakey.pem**.

 **Note:** PEM is a keyfile format standard.

**Step 4:** Export just your public key from your keyfile.

* Type **openssl rsa -in namersakey.pem -outform PEM -pubout -out namepubkey.pem** and press [Enter].
  + “**openssl rsa**” is a general command used for managing RSA keys.
  + “**-in namersakey.pem**” tells the computer to export the key from the namersakey.pem file.
  + “**-outform PEM**” tells the computer to format the output in PEM format.
  + “**-pubout**” tells the computer to output just the public key (which is important!).
  + “**-out namepubkey.pem**” tells the computer what file to write the public key to.

**Step 5:** View your private and public keys (these keys are encoded in Base64).

* Type **cat namersakey.pem** and press [Enter] to view your private key.
* Type **cat namepubkey.pem** and press [Enter] to view your public key.

**Step 6:** Encrypt your AES key you created in lab 1 (**namesymkey.bin**) with RSA

* Type **openssl rsautl -encrypt -inkey namepubkey.pem -pubin -in namesymkey.bin -out namesymkey.bin.enc** and press [Enter].
  + “**openssl rsautl**” is a general rsa encryption utility tool.
  + “**-encrypt**” tells the computer we want to encrypt data (this is not strictly necessary as encryption is the default).
  + “**-inkey namepubkey.pem**” designates the file with the public encryption key.
  + “**-pubin**” tells the computer that the input file is an RSA public key.
  + “**-in namesymkey.bin**” designates the file to be encrypted.
  + “**-out namesymkey.bin.enc**” designates the file to output the encrypted data to.
* Type **cat namesymkey.bin.enc** and press [Enter] to view the content of the encrypted file (it should be gibberish).

**Step 7:** Decrypt your key.

* Type **openssl rsautl -decrypt -inkey namersakey.pem -in namesymkey.bin.enc -out decryptsymkey.bin** and press [Enter].
  + “**openssl rsautl**” is a general rsa encryption utility tool.
  + “**-decrypt**” indicates that we’ll be decrypting instead of encrypting.
  + “**-inkey namersakey.pem**” designates the file that holds the private decrypt key.
  + “**-in namesymkey.bin.enc**” designates the file to be decrypted.
  + “**-out decryptsymkey.bin**” designates the file to output the decrypted data to.

**Step 8:** View the contents of the original file and the decrypted file to compare (they should be the same).

* Type **cat decryptsymkey.bin** and press [Enter].
* Type **cat namesymkey.bin** and press [Enter].

The contents of the files should match.

**Step 9:** Concept Check

Type **ls -l** and press [Enter].

You should see a file called **teacherpubkey.pem**.

Use your teacher’s public rsa key to encrypt your **namesymkey.bin** file. Note that you already created a file called **namesymkey.bin.enc** when you encrypted your symmetric key using your own rsa key. So, this time call it **namesymkey1.bin.enc** so that the files are uniquely named.

**Step 10:** Submit your work to your teacher.

Submit your **namesymkey1.bin.enc** file to your teacher.


