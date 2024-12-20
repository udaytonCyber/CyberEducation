LESSON OVERVIEW

Chapter 2: Asymmetric Encryption

Lesson Description

Students  will  learn  about  asymmetric  cryptography  in  contrast  to  the  symmetric  algorithms
learned in the previous chapter. Students will learn about RSA as an example of an asymmetric
encryption algorithm and how it works. Emphasis is given to understanding the role of the key
pair  in  contrast  to  the  single  key  used  in  symmetric  encryption.  Kerckhoff’s  Principle  is
introduced as well.

Time Required:   Click or tap here to enter text.

Level:

☒  Beginner

☐  Intermediate

☐  Advanced

Audience:

☒  K-12

☒  Higher Education

☐  Adult /Workforce Development

Lesson Learning Outcomes:

Students will:
•  Understand how asymmetric cryptography works and be able to describe how it contrasts

with symmetric cryptography.

•  Understand  how  asymmetric  cryptography  is  combined  with  symmetric  cryptography  to

create a fast and secure cryptographic system.

•  Understand how RSA scrambles information in a reversible way to obfuscate the original data.
•  Be able to use OpenSSL to encrypt a file using RSA.

Lesson Prerequisite Knowledge

To fully understand RSA, students need to have an understanding of modular arithmetic, and
one-way functions. However, their understanding of these topics can be fairly elementary to
grasp the fundamentals of what is going on.

Prior Knowledge Alignments:

•  CompTIA Security+ Certification Objective 2.8

Created by:Click or tap here to enter text.
Contributors:Click or tap here to enter text.
Copyright © 2020, University of Cincinnati, Ohio. All rights reserved.

Ver. 1.0

LESSON OVERVIEW

Required Materials:

The lab documents are designed to be used with a pre-configured virtual machine on the Ohio
Cyber Range, however, they can be implemented on any device running OpenSSL commands.

Created by:Click or tap here to enter text.
Contributors:Click or tap here to enter text.
Copyright © 2020, University of Cincinnati, Ohio. All rights reserved.

Ver. 1.0

LESSON OVERVIEW

Lesson Instructional and Assessment Materials:

Instructor Resources

•  Chapter 2: Asymmetric Encryption Presentation (Slide Deck)
•  Cryptography Chapter 2 Assessment (Suggested assessment questions)
•  Cryptography Lab 2: RSA Encryption
•

lab2check.sh (A bash script to auto-check student lab submissions in the teacher account on
the associated VM; also available via my Github repository)
Introduction to Ciphers and Cryptography (A student-facing text designed to accompany
and support the information in the presentations.)

•

Instructional Materials

Chapter 2: Asymmetric Encryption Presentation
Time Required: Two 45-minute sessions

Description: Discusses the difference between symmetric and asymmetric encryption
algorithms and uses RSA as an example of a common asymmetric encryption algorithm.
Discusses the RSA key pair generation algorithm and the encryption and decryption process.
Discussion of how secure RSA is (and what length keys are required). Students are introduced
to how asymmetric encryption and symmetric encryption are used together to securely
establish a shared secret key. Kerckhoff’s principle is introduced.

Student Textbook: Introduction to Ciphers and Cryptography
Time Required: Used throughout every module

Description: A student-facing text designed to provide asynchronous content for students that
aligns with the content in the presentations. The student text also has a variety of helpful
appendices.

Created by:Click or tap here to enter text.
Contributors:Click or tap here to enter text.
Copyright © 2020, University of Cincinnati, Ohio. All rights reserved.

Ver. 1.0

LESSON OVERVIEW

Assessment Materials

Suggested Assessment Questions for Chapter 2
Time Required: If all ten questions were used, each assessment would be 15-25 minutes

Description: Ten suggested assessment questions: 5 auto-grade style questions (fill in the blank,
multiple choice, or select all style questions), and 5 open-ended response questions. A
suggested key is provided for each as well. The assessment questions are in plain text that an
instructor could copy and paste into any learning management system. Instructors can use
some, all, or none of the questions provided to suit their individual needs.

Lab 2: RSA Encryption
Time Required: 20-30 minutes

Description: In this lab, students generate an RSA key pair and export the public key. Students
investigate the format of their RSA key files. Then students use RSA to encrypt their symmetric
key from Lab 1 and decrypt it as well. Finally, students have the teacher’s public key and use
that public key to encrypt their own symmetric key file from Lab 1. Students submit their
encrypted symmetric key to the instructor. The teacher public and private keys are on the VM
provided by the OCRI, but they are also included in the folder with the documents if an
instructor wants to use them in another way.

Supplemental Materials

The following are provided for the instructor as supplemental materials:

•  Cryptography Labs General Notes for the Instructor
•

Introduction to Cryptography Overview

Created by:Click or tap here to enter text.
Contributors:Click or tap here to enter text.
Copyright © 2020, University of Cincinnati, Ohio. All rights reserved.

Ver. 1.0


