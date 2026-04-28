# EduFlow — LMS Core Architecture

Formal UML architectural design for **EduFlow**, an E-Learning Management System (LMS). Includes comprehensive Use Case, Sequence, and Activity diagrams detailing Teacher–Student interactions, automated scheduling logic, and lesson execution workflows. Built with PlantUML for version-controlled system modelling.

---

## Project Overview

EduFlow is a web-based LMS that supports three primary user roles:

| Role    | Key Responsibilities |
|---------|----------------------|
| Student | Create account, enrol in courses, view materials, submit assignments |
| Teacher | Set & update schedules, conduct live lessons, upload materials, grade work |
| Admin   | Manage users, approve accounts, generate reports |

---

## System Architecture

```
docs/
├── diagrams/
│   ├── use-case/
│   │   └── System_UseCase.puml          ← Full system use-case diagram
│   ├── activity/
│   │   └── Teacher_Master_Swimlane.puml ← Teacher workflow swimlane
│   └── sequence/
│       ├── Teacher_SetSchedule_Seq.puml  ← Set & Update Schedule
│       ├── Teacher_ConductLesson_Seq.puml← Conduct Live Lesson
│       └── Teacher_UploadMaterials_Seq.puml ← Upload Materials
└── requirements/
    └── Software_Requirements_Spec.md    ← SRS v1.0
assets/                                  ← Rendered diagram images (PNG/SVG)
```

---

## UML Diagrams

### System Use Case Diagram
> `docs/diagrams/use-case/System_UseCase.puml`

![System Use Case](assets/System_UseCase.png)

*Key relationships:*
- `(Create Account) ..> (Require Approval) : <<extend>>` — Approval is an optional extension triggered for restricted account types.
- `(Update Schedule) ..> (Set Schedule) : <<extend>>` — Updating is an optional extension of the base scheduling action.

---

### Teacher Activity Swimlane
> `docs/diagrams/activity/Teacher_Master_Swimlane.puml`

![Teacher Swimlane](assets/Teacher_Master_Swimlane.png)

---

### Sequence Diagrams

| Scenario | File |
|----------|------|
| Set / Update Schedule | `docs/diagrams/sequence/Teacher_SetSchedule_Seq.puml` |
| Conduct Lesson | `docs/diagrams/sequence/Teacher_ConductLesson_Seq.puml` |
| Upload Materials | `docs/diagrams/sequence/Teacher_UploadMaterials_Seq.puml` |

---

## Requirements

See [Software Requirements Specification](docs/requirements/Software_Requirements_Spec.md) for full functional and non-functional requirements.

---

## Rendering Diagrams

Install the [PlantUML VS Code extension](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml) or use the [PlantUML online server](https://www.plantuml.com/plantuml/uml/) to render `.puml` files.

```bash
# Generate all diagrams (requires Java + plantuml.jar)
java -jar plantuml.jar docs/**/*.puml -o ../../../assets
```
