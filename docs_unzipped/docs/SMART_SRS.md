# Software Requirements Specification
for
**EduFlow: E-Learning System**

**Version:** 1.0 approved  
**Prepared by:** AI Assistant  
**Organization:** TAJ-LMS Team  
**Date created:** May 1, 2026  

---

## Table of Contents
1. [Introduction](#1-introduction)
2. [Overall Description](#2-overall-description)
3. [External Interface Requirements](#3-external-interface-requirements)
4. [System Features](#4-system-features)
5. [Other Nonfunctional Requirements](#5-other-nonfunctional-requirements)
6. [Other Requirements](#6-other-requirements)

---

## Revision History
| Name | Date | Reason For Changes | Version |
|---|---|---|---|
| AI Assistant | 2026-05-01 | Initial Draft based on UML specifications | 1.0 |

---

## 1. Introduction

### 1.1 Purpose 
The purpose of this document is to define the Software Requirements Specification (SRS) for the **EduFlow: (Student Management And Resource Tracking) E-Learning System**. This document outlines the functional and non-functional requirements of the system, acting as a comprehensive guide for developers, project managers, and stakeholders. It covers the entire scope of the EduFlow: system, including user authentication, subscription, scheduling, and lesson management.

### 1.2 Document Conventions
This document follows the IEEE formatting standard for SRS. Priority levels (High, Medium, Low) are assigned to system features to guide the development phases. Requirements are identified by unique tags (e.g., `REQ-AUTH-1`).

### 1.3 Intended Audience and Reading Suggestions
This document is intended for:
- **Developers & QA Testers:** To understand technical implementations and write test cases.
- **Project Managers:** To track feature development and define milestones.
- **Stakeholders & Business Analysts:** To ensure alignment with business objectives.
*Suggestion:* Readers are advised to start with Section 2 to grasp the overall system context before proceeding to detailed technical constraints in Sections 3 and 4.

### 1.4 Product Scope
EduFlow: is an advanced E-Learning platform designed to streamline online education by connecting students and teachers. Its primary objectives include automating course subscriptions, scheduling classes, processing secure payments, and providing a robust environment for virtual lessons (including file sharing and session recording). By minimizing administrative overhead, EduFlow: allows educators to focus on teaching while providing students with a seamless, intuitive learning experience.

### 1.5 References
- **Use Case Architecture:** `docs/diagrams/use-case/useCase.puml`
- **Sequence Diagrams:** `docs/diagrams/sequence/`

---

## 2. Overall Description

### 2.1 Product Perspective
EduFlow: is a new, self-contained E-Learning software product. It replaces fragmented educational tools by centralizing scheduling, video lessons, and payment processing into a single web-based application. 

### 2.2 Product Functions
Based on the system's architecture, EduFlow: provides the following major functions:
- **Authentication & Security:** Login, Registration, Password Reset, Email Verification, and Admin Approval.
- **Payment & Subscription:** Course subscription, time-slot selection, automated bank transactions, and discount applications.
- **Scheduling Management:** Availability checking, setting/updating schedules, and lesson rescheduling.
- **Virtual Classroom:** Live lesson conduction, attendance, problem reporting, and session recordings.
- **Resource Management:** Uploading, validating, replacing, and deleting educational materials (PDFs & Videos).

### 2.3 User Classes and Characteristics
- **Student:** Active learners who browse courses, make payments, attend lessons, and report technical issues. Needs an intuitive and highly accessible UI.
- **Teacher:** Educators who set availability schedules, conduct lessons, and upload course materials. Requires a dashboard for resource and schedule management.
- **Admin:** System administrators responsible for verifying/approving new teacher accounts and resolving platform-level issues.
- **Bank (External Actor):** An automated external system responsible for securely processing financial transactions.

### 2.4 Operating Environment
- **Platform:** Web-based (accessible via Chrome, Firefox, Safari, Edge).
- **Client Devices:** Desktops, Laptops, and Mobile Devices (Responsive Design).
- **Server:** Cloud-hosted environment (e.g., AWS, Azure) running a modern web server and relational database (e.g., PostgreSQL/MySQL).

### 2.5 Design and Implementation Constraints
- **Payment Security:** Must strictly adhere to PCI-DSS standards for processing transactions.
- **Media Hosting:** Video recordings and large PDFs require an optimized cloud storage solution (e.g., AWS S3).
- **Communication Protocol:** All data must be encrypted using HTTPS/TLS.

### 2.6 User Documentation
- **On-boarding Tutorials:** Interactive walk-throughs for new Teachers and Students.
- **Knowledge Base:** Online FAQ and troubleshooting guides for common scheduling or payment issues.

### 2.7 Assumptions and Dependencies
- **Dependencies:** Relies on third-party Bank APIs for transaction processing and potentially external providers for email notifications (e.g., SendGrid).
- **Assumptions:** Users have access to a stable internet connection for participating in live video lessons.

---

## 3. External Interface Requirements

### 3.1 User Interfaces
- **Student Dashboard:** Displays upcoming lessons, subscribed courses, and active assignments.
- **Teacher Dashboard:** Displays calendar for scheduling, file management hub, and lesson launching capabilities.
- **Consistency:** The UI will follow a unified design system with standard navigation bars, modal confirmations for destructive actions (e.g., deleting a file), and consistent error message formatting.

### 3.2 Hardware Interfaces
- **Peripherals:** Requires access to client device microphones and webcams for the Virtual Classroom module.

### 3.3 Software Interfaces
- **Payment Gateway API:** Interfaces with Bank/Payment Processor to handle JSON-based transaction requests and webhook callbacks.
- **Storage API:** Interfaces with Cloud Storage for saving and retrieving uploaded PDFs and MP4 videos.

### 3.4 Communications Interfaces
- **HTTPS:** Port 443 for all web traffic to ensure data privacy.
- **SMTP:** For dispatching system alerts, email verifications, and schedule notifications.
- **WebRTC/WebSockets:** For low-latency live video streaming and real-time chat during lessons.

---

## 4. System Features

### 4.1 Authentication and User Management
#### 4.1.1 Description and Priority
**Priority: High.** The system must securely handle user identity, registration, and role-based access. Admin approval is required for teacher accounts.
#### 4.1.2 Stimulus/Response Sequences
- *Stimulus:* User submits registration form.
- *Response:* System sends verification email.
- *Stimulus:* Admin reviews pending Teacher.
- *Response:* System updates teacher status to 'Approved' and notifies them.
#### 4.1.3 Functional Requirements
- `REQ-AUTH-1:` The system shall allow users to register as either a Student or a Teacher.
- `REQ-AUTH-2:` The system shall enforce email verification before initial login.
- `REQ-AUTH-3:` The system shall require Admin approval for Teacher accounts before they can set schedules.

### 4.2 Payment and Subscription Management
#### 4.2.1 Description and Priority
**Priority: High.** Students must be able to choose specific slots, apply discounts, and execute payments.
#### 4.2.2 Stimulus/Response Sequences
- *Stimulus:* Student selects a slot and enters payment details.
- *Response:* System processes transaction via Bank API and confirms subscription.
#### 4.2.3 Functional Requirements
- `REQ-PAY-1:` The system shall lock the selected slot temporarily while payment is processing.
- `REQ-PAY-2:` The system shall apply valid discount codes to the total price before transaction.
- `REQ-PAY-3:` The system shall generate a digital receipt upon successful transaction.

### 4.3 Scheduling System
#### 4.3.1 Description and Priority
**Priority: High.** Teachers manage availability; Students and Teachers can request rescheduling based on system rules.
#### 4.3.2 Stimulus/Response Sequences
- *Stimulus:* Teacher updates their weekly schedule.
- *Response:* System validates against existing bookings and confirms schedule.
#### 4.3.3 Functional Requirements
- `REQ-SCH-1:` The system shall prevent double-booking of any given time slot.
- `REQ-SCH-2:` The system shall automatically send notifications to affected parties if a lesson is rescheduled.

### 4.4 Virtual Classroom and Lessons
#### 4.4.1 Description and Priority
**Priority: High.** The core environment where learning takes place, including video/audio features and problem reporting.
#### 4.4.2 Stimulus/Response Sequences
- *Stimulus:* Teacher clicks "Conduct Lesson".
- *Response:* System initializes the virtual classroom environment.
#### 4.4.3 Functional Requirements
- `REQ-CLS-1:` The system shall allow Teachers to start, pause, and end a lesson.
- `REQ-CLS-2:` The system shall allow users to report technical problems during an active session.
- `REQ-CLS-3:` The system shall support automatic uploading of the lesson recording post-session.

### 4.5 Content and File Management
#### 4.5.1 Description and Priority
**Priority: Medium.** Teachers can upload, validate, replace, and delete course materials.
#### 4.5.2 Stimulus/Response Sequences
- *Stimulus:* Teacher uploads a PDF.
- *Response:* System validates file size/type and stores it securely.
#### 4.5.3 Functional Requirements
- `REQ-FILE-1:` The system shall restrict uploads to standard formats (.pdf, .mp4) and validate file integrity.
- `REQ-FILE-2:` The system shall allow Teachers to replace existing files without breaking student links.

---

## 5. Other Nonfunctional Requirements

### 5.1 Performance Requirements
- The system web pages shall load in under 2.5 seconds on standard broadband connections.
- The Virtual Classroom must support concurrent connections without significant audio/video latency (target < 500ms).

### 5.2 Safety Requirements
- In the event of a transaction failure, the system must immediately revert to a safe state, ensuring no funds are lost and the user is notified.
- Database backups must be executed daily to prevent critical data loss.

### 5.3 Security Requirements
- All user passwords must be hashed using strong algorithms (e.g., bcrypt).
- User sessions must expire automatically after 24 hours of inactivity.
- All endpoints processing personal or financial data must require strict bearer token authentication.

### 5.4 Software Quality Attributes
- **Availability:** The system shall strive for 99.9% uptime.
- **Usability:** The interface must be intuitive, requiring less than 15 minutes of training for a new Teacher to set a schedule and conduct a lesson.
- **Reliability:** Failed file uploads should auto-retry where possible.

### 5.5 Business Rules
- `BR-1:` A Student cannot attend a lesson without a verified, successful payment.
- `BR-2:` A Teacher cannot accept  or conduct lessons until explicitly approved by an Admin.
- `BR-3:` Lessons can only be rescheduled with at least 24 hours prior notice.

---

## 6. Other Requirements
- **Localization:** The platform interface should support Internationalization (i18n), initially supporting English and Arabic to cater to regional demographics.

---

### Appendix A: Glossary
- **EduFlow::** Student Management And Resource Tracking.
- **UI:** User Interface.
- **PCI-DSS:** Payment Card Industry Data Security Standard.
- **WebRTC:** Web Real-Time Communication.

### Appendix B: Analysis Models
*(Refer to `docs/diagrams/use-case/useCase.puml` for detailed UML Use Case models illustrating the interactions between Students, Teachers, Admins, and external Bank systems.)*

### Appendix C: To Be Determined List
1. `TBD-1`: Specific payment gateway provider (e.g., Stripe, PayPal, Local Bank Gateway).
2. `TBD-2`: Maximum allowed file size for video uploads.
3. `TBD-3`: Exact logic and penalty rules for late rescheduling.
