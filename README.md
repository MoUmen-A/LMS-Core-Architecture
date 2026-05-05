# EduFlow: LMS Core Architecture

EduFlow is an e-learning system architecture focused on secure payments, reliable scheduling, and a scalable virtual classroom. This repository showcases the core architecture artifacts (SRS, use cases, and UML flows) built with an architectural engineer mindset: clear boundaries, risk-driven requirements, and traceable behavior from actors to features.

## Why this architecture stands out

- **End-to-end traceability:** Requirements in the SRS are mapped to use cases and sequence flows, enabling consistent validation from stakeholder needs to system behavior.
- **Risk-first design:** Security, payment compliance (PCI-DSS), and safe transactional rollback are treated as first-class drivers, not afterthoughts.
- **Scalable learning core:** The design separates scheduling, payments, and virtual classroom concerns to support horizontal scaling and reduce cross-module coupling.
- **Operational readiness:** Nonfunctional requirements address performance targets, availability, backups, and session control, aligning with production realities.
- **Clear actor boundaries:** Distinct student, teacher, admin, and bank roles reduce ambiguity and improve access control and auditability.

## What is included

- **SRS:** Comprehensive functional and nonfunctional requirements with unique tags and priorities.
- **Use-case diagrams:** Actor-driven view of system goals and responsibilities.
- **Sequence diagrams:** Detailed interaction flows for key scenarios (lesson conduct, join lesson, reschedule, payment).
- **Class diagram:** Core domain abstractions for the learning platform.

## Where to start

- Read the SRS: [docs/EduFlow_SRS.md](docs/EduFlow_SRS.md)
- Review use cases: [docs/diagrams/use-case](docs/diagrams/use-case)
- Inspect sequences: [docs/diagrams/sequence](docs/diagrams/sequence)
- Check class diagram: [docs/diagrams/class-diagram](docs/diagrams/class-diagram)

## Diagram structure

- `docs/diagrams/sequence/TEACHER` - teacher-facing sequence diagrams
- `docs/diagrams/sequence/USER` - student-facing sequence diagrams
- `docs/diagrams/use-case` - UML use-case diagrams
- `docs/diagrams/class-diagram` - UML class diagrams

## Render PlantUML diagrams

1. Install the VS Code PlantUML extension or use `plantuml.jar` directly.
2. Ensure Java is installed and on your PATH.
3. Open a `.puml` file and use the PlantUML preview command, or run:

```powershell
java -jar "path\to\plantuml.jar" "conduct_lesson.puml" -tsvg -o "output-folder"
```

If diagrams fail to render with a "no image" warning, ensure the `.puml` file contains a valid `@startuml`/`@enduml` block and non-empty diagram content.

To render all diagrams to `docs/diagrams/plantuml-output`:

```powershell
java -jar "C:\Users\Momen\AppData\Roaming\Code\User\globalStorage\justuskarlsson.plan-uml\plantuml-1.2025.10.jar" ./docs/diagrams/** -tsvg -o ./docs/diagrams/plantuml-output
```
