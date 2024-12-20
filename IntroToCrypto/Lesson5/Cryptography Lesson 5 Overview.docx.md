
# Chapter 5: Digital Certificates and PKI

## Lesson Description

Students will learn about how digital certificates contribute to creating a distributed eco-system of trust in a semi-anonymous online environment. Students learn what a digital certificate is, and how web browsers use SSL certificates to authenticate websites. Students learn about the role of certificate authorities, and the life cycle of a digital certificate.

Time Required: Click or tap here to enter text.

Level:

☒ Beginner

☐ Intermediate

☐ Advanced

Audience:

☒ K-12

☒ Higher Education

☐ Adult /Workforce Development

## Lesson Learning Outcomes:

Students will:

* Understand the role of digital certificates in PKI.
* Understand the contents and structure of a digital certificate.
* Understand the life cycle of a digital certificate.
* Understand how web browsers use SSL certificates to authenticate websites.

## Lesson Prerequisite Knowledge

Students will need to understand how digital signatures and RSA keys work. These topics are covered in Chapters 2 and 4.

## Prior Knowledge Alignments:

* CompTIA Security+ Certification Objective 3.9

## Required Materials:

The lab documents are designed to be used with a pre-configured virtual machine on the Ohio Cyber Range, however, they can be implemented on any device running OpenSSL commands.

# Lesson Instructional and Assessment Materials:

## Instructor Resources

* Chapter 5: Digital Certificates (Slide Deck)
* Cryptography Chapter 5 Assessment (Suggested assessment questions)
* Cryptography Lab 5: Digital Certificates
* lab5check.sh (A bash script to auto-check student lab submissions in the teacher account on the associated VM; also available via [my Github](https://www.github.com/bendougherty) repository)
* Introduction to Ciphers and Cryptography (A student-facing text designed to accompany and support the information in the presentations.)

## Instructional Materials

### Chapter 5: Digital Certificates Presentation

**Time Required:** One 45-minute session

**Description:** Introduces the role of digital certificates using examples from the physical world. Discusses what digital certificates are, what they contain, and how they create a digital distributed eco-system of trust in an online environment. Types of certificates and the life cycle of a digital certificate are both discussed.

### Student Textbook: Introduction to Ciphers and Cryptography

**Time Required:** Used throughout every module

**Description:** A student-facing text designed to provide asynchronous content for students that aligns with the content in the presentations. The student text also has a variety of helpful appendices.

## Assessment Materials

### Suggested Assessment Questions for Chapter 5

**Time Required:** If all ten questions were used, each assessment would be 15-25 minutes

**Description:** Ten suggested assessment questions: 5 auto-grade style questions (fill in the blank, multiple choice, or select all style questions), and 5 open-ended response questions. A suggested key is provided for each as well. The assessment questions are in plain text that an instructor could copy and paste into any learning management system. Instructors can use some, all, or none of the questions provided to suit their individual needs.

### Lab 5: Digital Certificates

**Time Required:** 30-40 minutes

**Description:** In this lab students generate their own self-signed digital certificate to make themselves a certificate authority. Then students generate a certificate signing request file (CSR) for a fictional company, and use their CA to digitally sign the CSR and issue a signed digital certificate for the fake company. For this to work there are several special elements that have been configured on the student VM, and students need to follow the instructions carefully.

## Supplemental Materials

The following are provided for the instructor as supplemental materials:

* Cryptography Labs General Notes for the Instructor
* Introduction to Cryptography Overview

