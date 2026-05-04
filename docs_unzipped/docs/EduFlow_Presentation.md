<div style="font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; background-color: #FAFAFA; color: #333333; padding: 40px; max-width: 900px; margin: 0 auto; line-height: 1.6;">

<!-- SLIDE 1: Title Slide -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 60px 40px; margin-bottom: 40px; text-align: center; box-shadow: 0 4px 6px rgba(0,0,0,0.05);">
    <h1 style="color: #005A9C; font-size: 3em; margin-bottom: 10px;">EduFlow</h1>
    <h2 style="color: #708090; font-size: 1.5em; font-weight: 400;">Student Management and Resource Tracking</h2>
    <hr style="border: 0; height: 1px; background-color: #E0E0E0; width: 50%; margin: 30px auto;">
    <p style="color: #708090; font-size: 1.1em;">Software Architecture & Technical Overview</p>
</div>

<!-- SLIDE 2: Executive Summary -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">Executive Summary</h2>
    <p style="font-size: 1.2em; color: #444; margin-top: 20px;">
        <strong>Streamlining online education through automated scheduling and secure resource management.</strong>
    </p>
    <p>EduFlow is a centralized E-Learning platform designed to bridge the gap between students and educators. By automating administrative overhead—such as course subscriptions, payment processing, and schedule management—EduFlow empowers teachers to focus on instruction while providing students with a seamless, intuitive, and secure learning experience.</p>
</div>

<!-- SLIDE 3: System Architecture -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">System Architecture</h2>
    <ul style="margin-top: 20px;">
        <li><strong>Platform:</strong> Responsive Web-based application accessible via modern browsers.</li>
        <li><strong>Environment:</strong> Cloud-hosted infrastructure ensuring high availability and scalability.</li>
        <li><strong>External Integrations:</strong> Secure Bank API integrations for seamless transaction processing and webhook callbacks.</li>
        <li><strong>Communication:</strong> HTTPS for all data traffic; WebRTC/WebSockets for low-latency live video streaming.</li>
    </ul>
    
    <div style="margin-top: 30px; padding: 40px; border: 2px dashed #B0C4DE; background-color: #F8F9FA; text-align: center; color: #708090; border-radius: 4px;">
        <em>[ Placeholder: High-Level System Architecture / Deployment Diagram ]</em>
    </div>
</div>

<!-- SLIDE 4: Core Functionality - Authentication -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">Core Functionality: Authentication</h2>
    <p>Secure identity and role-based access management.</p>
    <ul>
        <li><strong>Login & Registration:</strong> Secure account creation with mandatory email verification.</li>
        <li><strong>Role-Based Access:</strong> Distinct privileges for Students, Teachers, and Admins.</li>
        <li><strong>Critical Step:</strong> Teacher accounts require <strong>Admin Approval</strong> before they can set schedules or conduct lessons.</li>
    </ul>

    <div style="margin-top: 30px; padding: 40px; border: 2px dashed #B0C4DE; background-color: #F8F9FA; text-align: center; color: #708090; border-radius: 4px;">
        <em>[ Placeholder: Use Case Diagram - Authentication & User Management ]</em>
    </div>
</div>

<!-- SLIDE 5: Core Functionality - Scheduling -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">Core Functionality: Scheduling</h2>
    <p>Automated calendar management to prevent conflicts and ensure smooth operations.</p>
    <ul>
        <li><strong>Conflict-Checking Logic:</strong> The system automatically validates teacher availability and prevents double-booking of any time slot.</li>
        <li><strong>Availability Management:</strong> Teachers can easily set and update their weekly schedules.</li>
        <li><strong>Notification System:</strong> Automated SMTP email alerts dispatched to affected parties when lessons are booked or rescheduled.</li>
    </ul>

    <div style="margin-top: 30px; padding: 40px; border: 2px dashed #B0C4DE; background-color: #F8F9FA; text-align: center; color: #708090; border-radius: 4px;">
        <em>[ Placeholder: Activity Diagram - Schedule Creation and Conflict Resolution ]</em>
    </div>
</div>

<!-- SLIDE 6: Core Functionality - Virtual Classroom -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">Core Functionality: Virtual Classroom</h2>
    <p>The core environment where real-time learning takes place.</p>
    <ul>
        <li><strong>Live Session Initialization:</strong> Teachers can seamlessly start, pause, and end virtual lessons.</li>
        <li><strong>Automatic Session Recording:</strong> System supports the automatic capture and post-session upload of lesson recordings.</li>
        <li><strong>Real-Time Interaction:</strong> Utilizing WebRTC for low-latency video and audio communication.</li>
    </ul>

    <div style="margin-top: 30px; padding: 40px; border: 2px dashed #B0C4DE; background-color: #F8F9FA; text-align: center; color: #708090; border-radius: 4px;">
        <em>[ Placeholder: Sequence Diagram - Conduct Virtual Lesson & Auto-Record ]</em>
    </div>
</div>

<!-- SLIDE 7: Core Functionality - Content Management -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">Core Functionality: Content Management</h2>
    <p>Efficient handling of educational materials and resources.</p>
    <ul>
        <li><strong>Strict Validation:</strong> System restricts uploads to standard educational formats (e.g., PDF, MP4) and validates file integrity before storage.</li>
        <li><strong>Lifecycle Management:</strong> Teachers can replace existing files without breaking links for students, or permanently delete outdated content.</li>
        <li><strong>Cloud Storage Integration:</strong> Reliable storage solutions for handling large media files.</li>
    </ul>
    
    <div style="margin-top: 30px; padding: 40px; border: 2px dashed #B0C4DE; background-color: #F8F9FA; text-align: center; color: #708090; border-radius: 4px;">
        <em>[ Placeholder: Activity Diagram - File Upload and Validation Lifecycle ]</em>
    </div>
</div>

<!-- SLIDE 8: Non-Functional Requirements -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">Non-Functional Requirements</h2>
    <p>Ensuring system reliability, speed, and security.</p>
    <ul>
        <li><strong style="color: #005A9C;">Availability:</strong> Architecture is designed to strive for <strong>99.9% uptime</strong> to ensure uninterrupted learning.</li>
        <li><strong style="color: #005A9C;">Performance:</strong> Target page load times of <strong>under 2.5 seconds</strong>. Video streaming latency maintained under 500ms.</li>
        <li><strong style="color: #005A9C;">Security:</strong> Strict adherence to <strong>PCI-DSS</strong> standards for all payment processing. All passwords are encrypted utilizing strong hashing algorithms (e.g., bcrypt).</li>
    </ul>
</div>

<!-- SLIDE 9: Business Rules -->
<div style="background-color: #FFFFFF; border: 1px solid #E0E0E0; border-radius: 8px; padding: 40px; margin-bottom: 40px; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
    <h2 style="color: #005A9C; border-bottom: 2px solid #F0F0F0; padding-bottom: 10px; margin-top: 0;">System Business Rules</h2>
    <p>The core policies governing platform interactions.</p>
    <div style="background-color: #F8F9FA; border-left: 4px solid #005A9C; padding: 15px 20px; margin-top: 20px;">
        <p style="margin: 0 0 10px 0;"><strong>BR-1: Verified Payments</strong></p>
        <p style="margin: 0;">A Student is strictly prohibited from attending a lesson without a verified, successful payment.</p>
    </div>
    <div style="background-color: #F8F9FA; border-left: 4px solid #005A9C; padding: 15px 20px; margin-top: 20px;">
        <p style="margin: 0 0 10px 0;"><strong>BR-2: Teacher Verification</strong></p>
        <p style="margin: 0;">A Teacher cannot accept subscriptions, publish schedules, or conduct lessons until explicitly approved by an Admin.</p>
    </div>
    <div style="background-color: #F8F9FA; border-left: 4px solid #005A9C; padding: 15px 20px; margin-top: 20px;">
        <p style="margin: 0 0 10px 0;"><strong>BR-3: Rescheduling Notice</strong></p>
        <p style="margin: 0;">Lessons can only be rescheduled if at least 24 hours of prior notice is provided to the system.</p>
    </div>
</div>

</div>
