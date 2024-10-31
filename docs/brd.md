# Business Requirements Document (BRD) for JAMC Project

## 1. Executive Summary

The JAMC project is focused on creating an educational platform that enhances learning experiences for high school students in Vietnam. The platform’s primary goal is to deliver a personalized and flexible learning environment that supports both students and teachers. JAMC allows teachers to manage real-world classes, interact in a Q&A environment, and offer additional learning resources as monetizable **Modules**. This BRD outlines the project’s core objectives, business goals, and success metrics guiding JAMC’s development.

## 2. Business Goals and Objectives

### 2.1 Business Goals
- Personalize the learning experience to match each student's pace and learning style.
- Enable teachers to focus on individual progress, reducing repetitive teaching tasks.
- Facilitate a Q&A-driven, interactive classroom environment.
- Support digital classroom transformation with tools for online class and module management.

### 2.2 Business Objectives
- Increase student engagement through personalized tools and an interactive Q&A system.
- Equip teachers with tools to efficiently manage and monitor student progress.
- Develop a user-friendly platform that aligns with evolving educational standards in Vietnam.
- Foster critical thinking and engagement in a personalized learning environment.

## 3. Stakeholders

- **Teachers**: Create and manage classes, offer personalized Q&A, track student progress, and monetize specialized Modules.
- **Students**: Enroll in classes, participate in Q&A, access learning resources, and engage with Modules at their own pace.
- **School Administrators** (future): Oversee platform-wide activities and moderate content.
- **Platform Owners**: Manage platform scalability, ensure technical reliability, and maintain alignment with educational goals.

## 4. Scope of the Project

### 4.1 In-Scope
- **Class Management**: Functionality for teachers to manage real classes and track student progress.
- **Q&A System**: A structured Q&A system with private/public questions for enhanced student-teacher interactions.
- **User Registration and Onboarding**: Registration with options for OAuth or email.
- **Module Access**: Tools for creating and monetizing Modules, enabling students to engage with additional resources at their own pace.
- **Review System**: A system that helps students select teachers based on learning styles and feedback.

### 4.2 Out-of-Scope
- AI-driven content recommendations (reserved for future iterations).
- Advanced analytics beyond a basic dashboard.
- School-level administrative tools (future development).

## 5. Business Context and Background

In Vietnam, large class sizes can limit personalized learning, making it difficult for teachers to address each student’s unique needs. JAMC aims to **personalize the learning experience** by offering a Q&A system and resources accessible beyond the classroom. By allowing students to engage in self-paced learning through Modules, JAMC provides a solution that enhances the classroom experience.

Teachers often repeat content each year. By allowing teachers to store resources in Modules accessible outside their real class, JAMC optimizes teacher efficiency, letting them focus on personalized student support. The platform encourages both students and teachers to engage with learning content in an adaptable format that meets the needs of today’s educational challenges.

## 6. Functional Requirements Overview

The JAMC platform includes the following core functionalities:

### 6.1 User Registration & Onboarding
- **Roles**: Register as students, teachers, or admins, each with specific permissions.
- **Authentication**: Support for OAuth and email-based sign-up with verification.
- **Profile Setup**: Customized profile setup based on the user role.

### 6.2 Class and Module Management (Teacher Role)
- **Class Management**: Teachers create and manage classes, set schedules, and monitor student progress.
- **Module Creation**: Teachers create Modules containing learning resources that can be monetized.
- **Student Enrollment Control**: Teachers manage enrollment requests and set content access levels for Modules.
- **Q&A Moderation**: Teachers manage Q&A interactions and select best answers.

### 6.3 Learning and Engagement (Student Role)
- **Class Enrollment**: Students enroll in classes with teacher approval.
- **Module Access**: Students access Modules at their own pace, including video lessons, PDFs, quizzes, and assignments.
- **Progress Tracking**: Students track their course progress and complete tasks as assigned.
- **Credit Points and Badges**: Students earn points and badges for Q&A contributions and course completion.

### 6.4 Interactive Q&A System
- **Q&A Posting**: Students post course-related questions, categorized by tags.
- **Answering and Voting**: Participants engage in Q&A, with upvotes/downvotes to highlight quality content.
- **Best Answer Selection**: Teachers select the best answers to guide students.

### 6.5 Dashboard and Progress Analytics
- **Student Dashboard**: Displays class/module progress, Q&A notifications, and credit points.
- **Teacher Dashboard**: Allows tracking of student progress and engagement in Q&A.
- **Admin Dashboard**: Provides analytics, tag management, and oversight of flagged content.

### 6.6 Notifications and Alerts
- **Course Updates**: Notifications for new content and assignments.
- **Progress Alerts**: Teachers receive alerts for students deviating from the expected pace.
- **Module Recommendations**: AI recommends relevant Modules for continued learning.

### 6.7 Admin and Content Management
- **User Management**: Admins manage user accounts and permissions.
- **Content Moderation**: Admins oversee Q&A quality, manage tags, and monitor flagged content.

### 6.8 Security and Compliance
- **Data Security**: All transactions use TLS encryption and comply with GDPR and local data laws.
- **Role-Based Access Control**: Permissions are enforced by user roles.
- **Error Handling**: Clear error messages and server-side logging for troubleshooting.

## 7. Non-Functional Requirements Overview

### 7.1 Performance
- The platform should ensure smooth concurrent access with minimal latency.

### 7.2 Security
- Implement secure user authentication and data encryption for all transactions.

### 7.3 Usability
- Interface should support users with varying digital literacy levels.

### 7.4 Reliability
- Target 99.5% uptime, especially during school hours.

## 8. Success Metrics
- **Student Progress**: Monitor individual progress and improvements.
- **User Engagement**: Track Q&A activity and module completion.
- **Teacher Satisfaction**: Evaluate platform support for teachers in managing classes.
- **Platform Growth**: Measure the increase in registered users and active sessions.

## 9. Assumptions and Constraints

### 9.1 Assumptions
- Teachers are familiar with basic online class management.
- Students will engage more with self-paced learning when provided interactive tools.

### 9.2 Constraints
- Platform must comply with Vietnamese data protection and GDPR standards.
- Cloud infrastructure will support scalability and availability.

## 10. Risks and Mitigations

### 10.1 Risks
- **Low Adoption**: Possible hesitation from teachers or students to adopt.
- **Technical Challenges**: Risks of technical issues during peak hours.

### 10.2 Mitigations
- Conduct training sessions and gather feedback to enhance usability.
- Implement a robust support system for platform issues.

## 11. Placeholder for Diagrams
- **System Architecture Diagram**: _Image Placeholder_
- **User Flow Diagram**: _Image Placeholder_
- **Data Flow Diagram (DFD)**: _Image Placeholder_

## 12. Appendices

### 12.1 Glossary
- **OAuth**: Protocol for authorization via third-party accounts.
- **Q&A**: Structured system for question and answer interactions.
- **Credit System**: Incentive mechanism to encourage participation.
- **GDPR**: General Data Protection Regulation for data privacy.
