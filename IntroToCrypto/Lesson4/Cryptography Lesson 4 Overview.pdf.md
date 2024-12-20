LESSON OVERVIEW

Chapter 4: Digital Signatures

Lesson Description

Students  learn  about  methods  of  authentication.  Students  also  learn  how  asymmetric
encryption  (RSA  specifically)  can  be  used to  provide  both  source  integrity  and data  integrity.
Focus is placed on how the role of the public and private keys in signing is reversed from how
they are used in encryption. In the lab, students will digitally sign a document and verify a digital
signature.

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
•  Understand how digital signatures provide both source and data integrity.
•  Understand different methods of authentication.
•  Be able to generate a digital signature.
•  Be able to verify a digitally signed document.

Lesson Prerequisite Knowledge

Students will need to understand how RSA keys function as inverses of each other which is
covered in Chapter 2 of this module.

Prior Knowledge Alignments:

•  CompTIA Security+ Certification Objective 2.8

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

•  Chapter 4: Authentication and Digital Signatures (Slide Deck)
•  Cryptography Chapter 4 Assessment (Suggested assessment questions)
•  Cryptography Lab 4: Digital Signatures
•

lab4check.sh (A bash script to auto-check student lab submissions in the teacher account on
the associated VM; also available via my Github repository)
Introduction to Ciphers and Cryptography (A student-facing text designed to accompany
and support the information in the presentations.)

•

Instructional Materials

Chapter 4: Authentication and Digital Signatures Presentation
Time Required: One 45-minute session

Description: Slides cover various types of authentication and MFA, and discuss digital
signatures in the context of authentication providing both source and data integrity.

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

Suggested Assessment Questions for Chapter 4
Time Required: If all ten questions were used, each assessment would be 15-25 minutes

Description: Ten suggested assessment questions: 5 auto-grade style questions (fill in the blank,
multiple choice, or select all style questions), and 5 open-ended response questions. A
suggested key is provided for each as well. The assessment questions are in plain text that an
instructor could copy and paste into any learning management system. Instructors can use
some, all, or none of the questions provided to suit their individual needs.

Lab 4: RSA Authentication
Time Required: 20-30 minutes

Description: Students will use the RSA key they generated in Lab 2 to digitally sign the text file
they created in Lab 1. Then they will verify their own signature. On the student VM there is a
directory called lab4, which contains four invoices, a public key, and a digital signature.
Students are asked to verify which of the four invoices has a valid digital signature and is the
real invoice. Students submit their RSA public key and digital signature to the teacher at the
end of the lab.

Supplemental Materials

The following are provided for the instructor as supplemental materials:

•  Cryptography Labs General Notes for the Instructor
•

Introduction to Cryptography Overview

Created by:Click or tap here to enter text.
Contributors:Click or tap here to enter text.
Copyright © 2020, University of Cincinnati, Ohio. All rights reserved.

Ver. 1.0


