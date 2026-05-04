<div style="font-family: 'Segoe UI', Arial, sans-serif; max-width: 1000px; margin: auto; padding: 40px; color: #333; line-height: 1.6;">

<!-- SLIDE 1: TITLE -->
<div style="text-align: center; padding: 60px; background: linear-gradient(135deg, #005A9C 0%, #003366 100%); color: white; border-radius: 12px; margin-bottom: 40px;">
    <h1 style="font-size: 3.5em; margin: 0;">EduFlow</h1>
    <h3 style="font-weight: 300; opacity: 0.9;">Student Management & Resource Tracking</h3>
    <div style="width: 100px; height: 4px; background: #FFD700; margin: 20px auto;"></div>
    <p style="font-size: 1.2em;">Software Engineering - AAST Term Project</p>
    <p style="font-size: 0.9em; opacity: 0.7;">Presented by: [Your Name]</p>
</div>

<!-- SLIDE 2: MAPPING LOGIC -->
<div style="padding: 40px; background: #fff; border: 1px solid #eee; border-radius: 12px; margin-bottom: 40px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #005A9C; padding-bottom: 10px;">SRS Logic to Implementation Mapping</h2>
    <p>We have mapped the <b>SMART SRS</b> requirements directly to the logical handlers in our model repository:</p>
    <table style="width: 100%; border-collapse: collapse; margin-top: 20px;">
        <tr style="background: #f8f9fa; border-bottom: 2px solid #dee2e6;">
            <th style="padding: 12px; text-align: left;">SRS Requirement</th>
            <th style="padding: 12px; text-align: left;">Logic Handler (Model File)</th>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">REQ-AUTH (Authentication)</td>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">student_activity_v1_legacy.puml</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">REQ-PAY (Payment Processing)</td>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">useCase_v1_legacy.puml</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">REQ-SCH (Scheduling Logic)</td>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">reshual.puml & teacher_activity_v1_puml</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">REQ-CLS (Virtual Classroom)</td>
            <td style="padding: 12px; border-bottom: 1px solid #eee;">conduct_lesson.puml</td>
        </tr>
    </table>
</div>

<!-- SLIDE 3: USE CASE -->
<div style="padding: 40px; background: #fff; border: 1px solid #eee; border-radius: 12px; margin-bottom: 40px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);">
    <h2 style="color: #005A9C;">Use Case Diagrams</h2>
    <p><b>General Use Case:</b> Illustrates high-level interactions between Students, Teachers, and Admins, focusing on core goals like course subscription. It provides a roadmap of system boundaries and the primary actors involved in the E-Learning lifecycle.</p>
    <p><b>Misuse Case:</b> Analyzes system resilience by modeling potential threats alongside defensive mitigation strategies. It ensures security requirements like MFA and backups are explicitly linked to identified risks like identity theft.</p>
    <div style="background: #f0f4f8; padding: 15px; border-radius: 8px; font-size: 0.9em; color: #555;">
        <b>Files:</b> [useCase_v1_legacy.puml], [misuse_v1_legacy.puml]
    </div>
</div>

<!-- SLIDE 4: ACTIVITY FLOWS -->
<div style="padding: 40px; background: #fff; border: 1px solid #eee; border-radius: 12px; margin-bottom: 40px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);">
    <h2 style="color: #005A9C;">Activity Diagrams</h2>
    <p><b>Student Flows:</b> Models the dynamic behavior of the student lifecycle, from secure registration to the multi-step payment process. These ensure that conditional logic and retry loops for user inputs are handled in a robust manner.</p>
    <p><b>Teacher Flows:</b> Details operational workflows for educators, focusing on material validation and virtual classroom initialization. It highlights the critical path for managing schedules and ensuring teacher availability without conflicts.</p>
    <div style="background: #f0f4f8; padding: 15px; border-radius: 8px; font-size: 0.9em; color: #555;">
        <b>Files:</b> [student_activity_v1_legacy.puml], [teacher_activity_v1_legacy.puml]
    </div>
</div>

<!-- SLIDE 5: SEQUENCE & DYNAMICS -->
<div style="padding: 40px; background: #fff; border: 1px solid #eee; border-radius: 12px; margin-bottom: 40px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);">
    <h2 style="color: #005A9C;">Sequence Diagrams</h2>
    <p><b>Conduct Lesson:</b> Captures chronological interaction between Teacher, Server, and Media Server to provision and record live sessions. It details the synchronous messaging required to handle student joins and automatic session storage.</p>
    <p><b>Reschedule Lesson:</b> Defines time-ordered logic for updating existing bookings, including the mandatory conflict-checking step. It guarantees notifications are dispatched to all affected parties as part of an atomic update.</p>
    <div style="background: #f0f4f8; padding: 15px; border-radius: 8px; font-size: 0.9em; color: #555;">
        <b>Files:</b> [conduct_lesson.puml], [reshual.puml], [join_lesson.puml]
    </div>
</div>

<!-- SLIDE 6: CLASS & DATA -->
<div style="padding: 40px; background: #fff; border: 1px solid #eee; border-radius: 12px; margin-bottom: 40px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);">
    <h2 style="color: #005A9C;">Class Diagram</h2>
    <p><b>System Domain Model:</b> Defines the static structure of the platform by detailing attributes and relationships between entities like Users, Courses, and Lessons. It establishes the foundational data model, utilizing inheritance for user roles and composition for course-lesson hierarchies.</p>
    <div style="background: #f0f4f8; padding: 15px; border-radius: 8px; font-size: 0.9em; color: #555;">
        <b>Files:</b> [class_diagram_v1_legacy.puml]
    </div>
</div>

<!-- SLIDE 7: ARCHITECTURAL EVOLUTION -->
<div style="padding: 40px; background: #E3F2FD; border: 1px solid #BBDEFB; border-radius: 12px; margin-bottom: 40px;">
    <h2 style="color: #01579B;">Architectural Best Practices (v2)</h2>
    <p>Beyond basic requirements, our <b>Architectural Version (v2)</b> implementation introduces:</p>
    <ul style="color: #0277BD;">
        <li><b>Swimlanes:</b> Clear separation of Client, Server, and External Service concerns.</li>
        <li><b>Security-First Design:</b> Credential stuffing mitigation and session hijacking prevention.</li>
        <li><b>Cloud Native storage:</b> Decoupled file management utilizing Cloud Storage (S3) signatures.</li>
        <li><b>Atomic Scheduling:</b> Locking mechanisms to prevent race conditions during high-traffic booking.</li>
    </ul>
</div>

<!-- SLIDE 8: CONCLUSION -->
<div style="text-align: center; padding: 40px;">
    <h2 style="color: #005A9C;">Thank You!</h2>
    <p>Questions & Feedback</p>
</div>

</div>
