
# Chapter 3: Message Digests

## Lesson Description

Students will learn about hashing algorithms: how they work, their important properties, and the function they provide in a security context. Students will also learn about some common applications of hashing, and about rainbow table attacks.

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

* Understand the role of digital hashes in ensuring data integrity.
* Understand the important properties of digital hashes.
* Be able to generate a digital hash for a file.
* Understand the role of an HMAC, and how it uses symmetric encryption to ensure data integrity.
* Be able to generate an HMAC for a file.

## Lesson Prerequisite Knowledge

Students will need to have a basic understanding of binary operations (AND, OR, NOT, XOR).

## Prior Knowledge Alignments:

* CompTIA Security+ Certification Objective 2.1
* CompTIA Security+ Certification Objective 2.8
* CompTIA Security+ Certification Objective 4.5

## Required Materials:

The lab documents are designed to be used with a pre-configured virtual machine on the Ohio Cyber Range, however, they can be implemented on any device running OpenSSL commands.

# Lesson Instructional and Assessment Materials:

## Instructor Resources

* Chapter 3: Data Integrity Presentation (Slide Deck)
* Cryptography Chapter 3 Assessment (Suggested assessment questions)
* Cryptography Lab 3: Message Digests
* Lab3check.sh (A bash script to auto-check student lab submissions in the teacher account on the associated VM; also available via [my Github](https://www.github.com/bendougherty) repository)
* Introduction to Ciphers and Cryptography (A student-facing text designed to accompany and support the information in the presentations.)

## Instructional Materials

### Chapter 3: Data Integrity Presentation

**Time Required:** One 45-minute session

**Description:** Students learn about digital hashes: what they are, how they work, and what the important properties of hashes are. Several examples of hash implementations are provided, and a there is a discussion of rainbow table attacks (highlighting the importance of salted hashes).

### Student Textbook: Introduction to Ciphers and Cryptography

**Time Required:** Used throughout every module

**Description:** A student facing text designed to provide asynchronous content for students that aligns with the content in the presentations. The student text also has a variety of helpful appendices.

## Assessment Materials

### Suggested Assessment Questions for Chapter 3

**Time Required:** If all ten questions were used, each assessment would be 15-25 minutes

**Description:** Ten suggested assessment questions: 5 auto-grade style questions (fill in the blank, multiple choice, or select all style questions), and 5 open-ended response questions. A suggested key is provided for each as well. The assessment questions are in plain text that an instructor could copy and paste into any learning management system. Instructors can use some, all, or none of the questions provided to suit their individual needs.

### Lab 3: Message Digests

**Time Required:** 20-30 minutes

**Description:** Students practice using OpenSSL to generate message digests for files. Then students generate an HMAC for a file. On the student VM there is a directory called lab3, which contains a symmetric key, five secret message files, and an HMAC file. Only one of the secret files has an HMAC that matches. The students are asked to verify which of the five files is the “real” file based on the HMAC provided. Students submit the HMAC file they generated as part of the lab to the teacher.

## Supplemental Materials

The following are provided for the instructor as supplemental materials:

* Cryptography Labs General Notes for the Instructor
* Introduction to Cryptography Overview

