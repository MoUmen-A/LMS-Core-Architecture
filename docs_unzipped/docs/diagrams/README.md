# Diagrams

This folder contains PlantUML diagrams for the LMS architecture and flows.

Structure:

- `sequence/TEACHER` — teacher-facing sequence diagrams (e.g., conduct lesson, reschedule)
- `sequence/USER` — student-facing sequences (e.g., join lesson)
- `use-case` — UML use-case diagrams describing actors and goals

Note: This directory consolidates diagram files previously stored under `docs/diagrans` (misspelled). Those original files have been moved here to avoid redundancy — remove the old `docs/diagrans` folder if you no longer need it.

How to render:

1. Install the VS Code PlantUML extension or use the `plantuml.jar` directly.
2. Ensure Java is installed and on your PATH.
3. Open the `.puml` file in VS Code and use the PlantUML preview command, or run:

```powershell
java -jar "C:\Users\Momen\AppData\Roaming\Code\User\globalStorage\justuskarlsson.plan-uml\plantuml-1.2025.10.jar" ./docs/diagrams/** -tsvg -o ./docs/diagrams/plantuml-output
```

If diagrams fail to render with a "no image" warning, ensure the `.puml` file contains a valid `@startuml`/`@enduml` block and non-empty diagram content.

Actor-specific use-cases:

- `docs/diagrams/use-case/student_usecase.puml`
- `docs/diagrams/use-case/teacher_usecase.puml`
- `docs/diagrams/use-case/admin_usecase.puml`
- `docs/diagrams/use-case/bank_usecase.puml`

Main consolidated use-case diagram:

- `docs/diagrams/use-case/useCase.puml`
