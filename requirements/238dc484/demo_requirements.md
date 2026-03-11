Exam Management System
1. Introduction
1.1 Purpose

The purpose of the Exam Management System is to automate the process of managing examinations in educational institutions. The system allows administrators to create exams, teachers to manage question papers, and students to appear for exams and view results.

1.2 Scope

The system will allow administrators to manage users and exam schedules. Teachers can create question papers and evaluate results, while students can register for exams, take exams online, and view their results.

1.3 Definitions

Student – User who takes the exam.

Teacher – User who creates and manages exams.

Administrator – Person responsible for managing the system.

Exam – Test conducted for evaluating student knowledge.

2. Overall Description
2.1 Product Perspective

The Exam Management System will be a web-based application connected to a database to manage students, exams, questions, and results.

2.2 Product Functions

Major functions include:

User registration and login

Exam creation and scheduling

Question paper management

Online exam conduction

Automatic result generation

2.3 User Classes
User Type	Description
Student	Takes exams and views results
Teacher	Creates exams and manages questions
Administrator	Manages users and exam schedules
2.4 Operating Environment

Web browser (Chrome, Firefox, Edge)

Backend server (Java / Python / Node)

Database (MySQL / PostgreSQL)

3. Functional Requirements
FR1: User Registration

The system shall allow students and teachers to register in the system.

FR2: User Login

The system shall allow registered users to log in using their credentials.

FR3: Exam Creation

Teachers shall be able to create exams and upload questions.

FR4: Exam Scheduling

The administrator shall schedule exams with date and time.

FR5: Take Exam

Students shall be able to take exams online within the scheduled time.

FR6: Automatic Evaluation

The system shall automatically evaluate objective-type questions.

FR7: Result Generation

The system shall generate results after exam completion.

FR8: Result Viewing

Students shall be able to view their exam results.

4. Non-Functional Requirements
NFR1: Performance

The system should handle multiple students taking exams simultaneously.

NFR2: Security

User authentication and data protection must be ensured.

NFR3: Usability

The interface should be simple and easy for students and teachers to use.

NFR4: Reliability

The system should ensure that exam data and results are accurately stored.

NFR5: Availability

The system should be available during exam schedules without downtime.

5. System Features
5.1 User Management

Register students and teachers

Manage user accounts

5.2 Exam Management

Create exams

Schedule exams

Manage questions

5.3 Result Management

Evaluate exams

Generate results

Display student scores

6. External Interface Requirements
6.1 User Interface

A web-based interface for students, teachers, and administrators.

6.2 Database Interface

The system will store data such as:

Student records

Exam details

Question banks

Results

7. Constraints

Internet connection required for online exams.

Exams must be taken within scheduled time.

Only registered students can access exams.