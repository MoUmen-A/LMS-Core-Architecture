# Software Requirements Specification
## EduFlow — Learning Management System (LMS)

**Version:** 1.0  
**Status:** Draft  
**Date:** 2026-04-28

---

## 1. Introduction

### 1.1 Purpose
This document defines the functional and non-functional requirements for EduFlow, a web-based Learning Management System (LMS) designed to facilitate seamless interactions between students, teachers, and administrators.

### 1.2 Scope
EduFlow supports:
- Student account creation with optional approval workflows
- Teacher-led scheduling, live lessons, and material management
- Administrative oversight and reporting

### 1.3 Definitions
| Term | Definition |
|------|------------|
| LMS  | Learning Management System |
| UC   | Use Case |
| SRS  | Software Requirements Specification |

---

## 2. Overall Description

### 2.1 Product Perspective
EduFlow is a standalone web application with REST API backend, PlantUML-documented architecture, and a responsive frontend.

### 2.2 User Classes
| Class   | Description |
|---------|-------------|
| Student | Learner who enrols in courses, views materials, and submits assessments |
| Teacher | Educator who creates schedules, conducts lessons, and uploads materials |
| Admin   | Manages user accounts, generates reports, and oversees the system |

---

## 3. Functional Requirements

### 3.1 Account Management
| ID     | Requirement |
|--------|-------------|
| FR-001 | The system shall allow new users to register via a "Create Account" form. |
| FR-002 | The system shall trigger a "Require Approval" extension for institutional account types. |
| FR-003 | The system shall allow users to login with username and password. |
| FR-004 | The system shall allow users to reset their password via email. |

### 3.2 Scheduling
| ID     | Requirement |
|--------|-------------|
| FR-010 | Teachers shall be able to set a new lesson schedule with date, time, course, and title. |
| FR-011 | Teachers shall be able to update an existing schedule (Update Schedule <<extends>> Set Schedule). |
| FR-012 | The system shall notify enrolled students when a schedule is created or updated. |

### 3.3 Lesson Delivery
| ID     | Requirement |
|--------|-------------|
| FR-020 | Teachers shall be able to start and end live lesson sessions. |
| FR-021 | The system shall record live sessions automatically. |
| FR-022 | Recordings shall be made available to enrolled students after the session ends. |

### 3.4 Material Management
| ID     | Requirement |
|--------|-------------|
| FR-030 | Teachers shall be able to upload files (PDF, video, images) to courses. |
| FR-031 | Teachers shall be able to update or delete previously uploaded materials. |
| FR-032 | Students shall be notified when new materials are published. |

### 3.5 Assessment
| ID     | Requirement |
|--------|-------------|
| FR-040 | Students shall be able to submit assignments. |
| FR-041 | Teachers shall be able to grade submissions. |
| FR-042 | The system shall update the gradebook and notify students of their grades. |

---

## 4. Non-Functional Requirements

| ID      | Category       | Requirement |
|---------|----------------|-------------|
| NFR-001 | Performance    | Page load time shall not exceed 2 seconds under normal load. |
| NFR-002 | Security       | All data transmission shall use HTTPS/TLS 1.2+. |
| NFR-003 | Availability   | The system shall target 99.9% uptime. |
| NFR-004 | Scalability    | The system shall support up to 10,000 concurrent users. |
| NFR-005 | Usability      | The UI shall be responsive and accessible (WCAG 2.1 AA). |

---

## 5. UML Diagram References

| Diagram | File |
|---------|------|
| System Use Case | `docs/diagrams/use-case/System_UseCase.puml` |
| Teacher Activity Swimlane | `docs/diagrams/activity/Teacher_Master_Swimlane.puml` |
| Set / Update Schedule Sequence | `docs/diagrams/sequence/Teacher_SetSchedule_Seq.puml` |
| Conduct Lesson Sequence | `docs/diagrams/sequence/Teacher_ConductLesson_Seq.puml` |
| Upload Materials Sequence | `docs/diagrams/sequence/Teacher_UploadMaterials_Seq.puml` |

---

*End of SRS v1.0*
