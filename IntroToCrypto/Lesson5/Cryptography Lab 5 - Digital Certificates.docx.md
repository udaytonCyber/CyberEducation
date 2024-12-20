

**Introduction to Cryptography**

**Lab 5: Digital Certificates**

**Description:**

In this lab we will get hands-on experience generating, signing, and using digital certificates.

OpenSSL is an open-source toolkit that contains a variety of cryptography related functions. You can read more about this toolkit by visiting their website <https://www.openssl.org>. On their website, you can also find the manual pages describing how to use the toolkit. In this lab we’ll be using the following commands (with linked manual pages for review):

* [General OpenSSL Commands Manual Page](https://www.openssl.org/docs/man1.0.2/man1/)
* [OpenSSL x509 Manual Page](https://www.openssl.org/docs/man1.0.2/man1/x509.html) (**openssl x509** is the sub command we’ll use to generate, sign, and manage certificates)
* [OpenSSL req Manual Page](https://www.openssl.org/docs/man1.0.2/man1/openssl-req.html) (**openssl req** is the sub command we’ll use for creating and processing certificate requests)
* [OpenSSL ca Manual Page](https://www.openssl.org/docs/man1.0.2/man1/ca.html) (**openssl** ca is the sub command we’ll use for signing certificate requests)

**Objectives:**

1. Create your own certificate authority
2. Create a certificate signing request (CSR) for a fictional company.
3. Use your CA to sign your CSR to generate a signed certificate for your fictional company.

**Materials:**

This lab was developed as part of a module to be used with the Ohio Cyber Range (OCR). In that context, your teacher should have given you instructions for how to access a virtual Linux machine through the OCR. Some of the commands here assume that you are using the VM that is already setup in the OCR for this lab.

**Instructions**

**Note:** Where you see “**name**”, you should replace this with your own name. For example, in step 3 where it says “**nameca.key**”, I would type “**doughertyca.key**”.

**Step 1:** Log in to your VM as “**student**” using the password **Pa$$w0rd** (that is a zero after the “w”).

**Step 2:** In the top left corner, there is an “Applications” menu; hover over “System Tools” and select “Terminal”.

**Step 3:** Generate a Self-Signed Certificate for Your CA.

Certificates contain a public key, so we need to generate an RSA key pair as part of this process.

* Type **cd lab5** and press [Enter].

This command changes our working directory to the **lab5 directory** so that the files we generate will reside in this directory.

* Type **openssl genrsa -out nameca.key 4096** and press [Enter].
  + “**openssl genrsa**” tells the computer we’ll use OpenSSL’s genrsa subcommand.
  + “**-out nameca.key**” tells the computer to write the key file to a file named **nameca.key**.
  + “**4096**” tells the computer to make it a 4096-bit key.
* Type **openssl req -x509 -key nameca.key -sha256 -days 365 -out nameca.crt** and press [Enter]
  + “**openssl req**” tells the computer we’ll use OpenSSL’s req subcommand to generate a certificate.
  + “**-x509**” is the command to tell the computer to make it a self-signed certificate. Without the -x509 option, the “req” subcommand generates certificate signing requests (CSRs).
  + “**-key nameca.key**” tells the computer to generate the certificate using the key file you made.
  + “**-sha256**” tells the computer to use SHA256 as the hashing algorithm.
  + “**-days 365**” tells the computer that the certificate should be valid for 1 year.
  + “**-out nameca.crt**” tells the computer to write the certificate to a file called nameca.crt.

Here the computer will ask you for some information, this information will be used to create a distinguished name (DN) for your CA (see screenshot below). You will be prompted for the following information:

* Country Name:
* State or Province Name:
* Locality Name (city):
* Organization Name (company):
* Organizational Unit Name (department):
* Common Name (your name):
* Email Address (your email):

For “**Organization Name**” I suggest something like “**NameCertCo**”; for “**Organizational Unit**” you can leave this blank by entering a **“.”** in the field. The rest of the fields should be straight-forward.

![](data:image/png;base64...)

* Type **ls -l** and press [Enter].

You should see **nameca.key** and **nameca.crt**.

To see what is in these files, use the following commands:

**openssl rsa -in nameca.key -text -noout**

**openssl x509 -in nameca.crt -text -noout**

The “**-text**” option tells OpenSSL to output the file in standard text format, and the “**-noout**” option suppresses the printing of the Base64 encoded text.

Make sure you can identify the following elements from each of these files:

**From the key file:**

* The primes p and q and their product n.
* The public encryption key
* The private decryption key

**From the Certificate:**

* The public key and modulus
* What part of the certificate indicates that it is a CA certificate

**Step 4:** Generate a Certificate Signing Request (CSR) for a fictional company (use the format **namecompany** for your company. For example, mine would be **doughertycompany**)

* Type **openssl genrsa -out namecompany.key 4096** and press [Enter].

This is a command we have used several times now to generate an RSA keypair.

* Type **openssl req -new -key namecompany.key -sha256 -out namecompany.csr** and press [Enter].
  + “**openssl req**” activates the “request” subcommand of OpenSSL.
  + “**-new**” tells the computer we’re generating a new CSR file.
  + “**-key namecompany.key**” tells the computer where to find the key for the certificate we’re requesting.
  + “**-sha256**” tells the computer what hashing algorithm to use.
  + “**-out namecompany.csr**” tells the computer to write the CSR to a file named namecompany.csr.

You will be prompted for information similar to earlier. This time fill in the information based on the fictional company you have invented for this lab.

You will also be prompted for two additional pieces of information:

* A challenge password (which you can set to anything you want)
* An optional company name (which you should set to the same as the company name you entered for the CSR.
* Type **openssl req -in namecompany.csr -text -noout** and press [Enter].

This command will read out the contents of the CSR file in plain text.

**Step 5:** Use your CA that you created to sign the CSR for your made-up company.

**Note:** Normally, you would send your CSR to a company that is a legitimate certificate authority; but for the purposes of this lab, you will sign your CSR using the quasi-legitimate[[1]](#footnote-1) CA that you established.

* Type **openssl ca -config openssl.cnf -policy policy\_anything -md sha256 -days 365 -in namecompany.csr -out namecompany.crt -batch -cert nameca.crt -keyfile nameca.key** and press [Enter].
  + “**openssl ca**” tells the computer that you are going to use the certificate authority subcommand for OpenSSL.
  + “**-config openssl.cnf**” will use the configuration file in your current directory to sign the certificate.
  + “**-policy policy\_anything**” will allow us to avoid restrictions from the default policy.
  + “**-md sha256**” indicates that the hashing algorithm will be SHA256.
  + “**-days 365**” sets the expiration date for the certificate one year from today.
  + “**-in namecompany.csr**” is the certificate signing request file that is being signed.
  + “**-out namecompany.crt**” tells the computer to write the signed certificate to the **namecompany.crt** file.
  + For the remainder of this command “**-batch -cert nameca.crt -keyfile nameca.key**”

Practice looking things up in the documentation by looking up these options to see what they do!

* Type **ls -l** and press [Enter].

You should now see a namecompany.crt file.

* Type **openssl x509 -in namecompany.crt -text -noout** and press [Enter].
  + “**x509**” is the subcommand that manages certificates (see documentation).
  + “**-in namecompany.crt**” tells the command what file to read.
  + “**-text**” tells the command to output the file in standard text format.
  + “**-noout**” suppresses the output of the Base64 encoded certificate.
  + This command will let you view your company’s certificate in plain text. You should be able to identify:
    - Your own CA information as the “issuer”
    - The dates the certificate is valid
    - The RSA public key information for your company (the modulus and exponent)
    - An indication that this certificate is NOT a CA certificate

**Step 6:** Submit your work to your teacher.

Submit your **nameca.crt** and **namecompany.crt** files to your instructor.

**References**

This lab is a combination of some of my own ideas with the beginning of the SEED PKI lab. The SEED PKI lab goes several steps beyond what we have done here to use the signed certificate for a web server which is then accessed via another machine. If you’re interested in going further with these ideas, I encourage you to check out their lab [here](https://seedsecuritylabs.org/Labs_16.04/PDF/Crypto_PKI.pdf).

1. I use the term “quasi” here because you are legitimate to yourself (hopefully you trust yourself!), but you are not a legitimate CA from anyone else’s perspective! [↑](#footnote-ref-1)

