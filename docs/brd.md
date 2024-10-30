# Business Requirements Document (BRD) for JAMC Project

## 1. Executive Summary

The JAMC project is focused on creating a comprehensive online platform that enhances the educational experience for students in Vietnam’s high school system. The primary goal is to provide a personalized learning environment that supports individual student development while optimizing the teaching process for teachers. The platform offers tools for class management, an interactive Q&A system for continuous feedback, and an option for teachers to monetize their specialized content. This BRD outlines the core objectives, goals, and success metrics guiding the development of the JAMC platform.

## 2. Business Goals and Objectives

### 2.1 Business Goals

- Personalize the learning experience to accommodate each student's learning speed and style.
- Empower teachers to focus on individual student progress rather than repetitive teaching tasks.
- Create a more interactive and engaging classroom environment through continuous feedback and interaction.
- Support the digital transformation of the classroom by providing robust tools for online class management.

### 2.2 Business Objectives

- Increase student participation and motivation in learning through personalized tools and interactive Q&A sessions.
- Provide teachers with the ability to manage and monitor individual student progress efficiently.
- Create an intuitive and user-friendly platform that supports the evolving educational standards in Vietnam.
- Foster a learning environment that encourages critical thinking, inquiry, and student engagement.

## 3. Stakeholders

- **Teachers**: Create and manage classes, engage in personalized Q&A, monitor student progress.
- **Students**: Enroll in classes, participate in Q&A, access online resources, and learn at their own pace.
- **School Administrators** (future): Oversee platform-wide activities, moderate content.
- **Platform Owners**: Manage the technical and business aspects of the platform, ensure platform scalability and alignment with educational goals.

## 4. Scope of the Project

### 4.1 In-Scope

- Online class management functionalities for teachers, with a focus on tracking individual student progress.
- Q&A system with public and private questions, supporting personalized teacher-student interactions.
- User registration and onboarding using OAuth or email.
- Tools for creating and accessing online educational resources, allowing for self-paced learning.
- A review-based system to help students choose teachers that match their learning style.

### 4.2 Out-of-Scope

- AI-driven content recommendations (reserved for future releases).
- Advanced analytics and data visualization beyond the basic dashboard.
- In-depth administrative tools for managing school-level activities.

## 5. Business Context and Background

In Vietnam’s public high schools, large class sizes often make personalized learning difficult, leading to a lack of individualized attention for students. Teachers often struggle to address each student’s needs and questions within the limited classroom time, which can hinder a student’s ability to fully understand the material.

The core issue the JAMC project aims to solve is to **personalize the learning experience** for students. By creating an online platform, students can learn at their own pace and revisit material as needed. The platform includes a **Q&A system**, allowing students to ask questions outside of classroom hours, enabling continuous feedback and guidance from teachers. This system addresses the critical need for interaction and response, which is essential for effective learning.

Additionally, teachers often repeat the same lessons each year with minimal changes. JAMC aims to **optimize teacher efficiency** by providing a system where core lessons and resources can be accessed by students repeatedly without requiring teachers to re-deliver the same content every year. This allows teachers to focus on **individual student support and development**.

While monetization (such as paid courses) is a feature of the system, the primary focus is to improve the classroom experience by offering **customizable, student-centered learning tools**. Students can choose teachers who best suit their learning style based on reviews, and teachers can build their reputations while offering tailored educational content. This system encourages both student and teacher engagement, aiming to resolve the limitations of large, impersonal class settings in public schools.

JAMC is designed to **adapt to changes in educational materials** and curricula over time, allowing the platform to remain relevant even as new teaching resources are introduced. The ultimate goal is to foster a more interactive, personalized, and effective learning environment that benefits both students and teachers.

## 6. Functional Requirements Overview

The platform will include the following key functionalities:

- **Class Creation & Management**: Teachers can create classes, schedule sessions, manage student enrollments, and track individual progress.
- **Q&A System**: A dynamic system for students and teachers to ask and answer questions, supporting personalized feedback and visibility settings (public or private).
- **User Registration & Onboarding**: A streamlined registration process using OAuth or email, facilitating quick access to the platform.
- **Educational Resource Management**: A central repository for teachers to create and share learning resources, accessible by students at their own pace.
- **Review System**: A review-based system that helps students select the most suitable teachers for their needs.

## 7. Non-Functional Requirements Overview

### 7.1 Performance

- The platform should handle concurrent access by students and teachers without significant latency, ensuring a seamless user experience.

### 7.2 Security

- Use OAuth for secure user authentication and data encryption (TLS) for all sensitive transactions.

### 7.3 Usability

- The interface should be intuitive, with a focus on minimizing the learning curve for teachers and students, supporting a diverse range of digital literacy skills.

### 7.4 Reliability

- Ensure high availability during school hours, targeting 99.5% uptime, with reliable access to educational resources and Q&A interactions.

## 8. Success Metrics

- **Student Progress Tracking**: Measure individual student growth and performance improvements over time.
- **User Engagement**: Track metrics like Q&A participation, class enrollments, and active student engagement.
- **Teacher Satisfaction**: Assess how effectively the platform supports teachers in managing and personalizing their classes.
- **Platform Growth**: Monitor the increase in registered users, active sessions, and the usage of personalized learning tools.

## 9. Assumptions and Constraints

### 9.1 Assumptions

- Teachers are familiar with basic online platforms for class management.
- Students are motivated to engage in self-paced learning when given the right tools and resources.

### 9.2 Constraints

- Platform must adhere to Vietnamese data protection laws and GDPR standards.
- Deployment will rely on cloud infrastructure to handle scalability and availability.

## 10. Risks and Mitigations

### 10.1 Risks

- **Low User Adoption**: There is a risk that teachers or students may not adopt the platform as expected.
- **Difficulty in Personalization**: Challenges in tailoring the platform to each student's learning needs may arise.
- **Technical Issues**: Potential technical issues during peak hours could affect platform reliability.

### 10.2 Mitigations

- Conduct user training sessions to ensure teachers and students are comfortable with the platform.
- Gather user feedback regularly to improve the personalization features of the platform.
- Implement a robust technical support system to address platform issues promptly.

## 11. Placeholder for Diagrams

- **System Architecture Diagram**: _Image Placeholder_
- **User Flow Diagram**: _Image Placeholder_
- **Data Flow Diagram (DFD)**: _Image Placeholder_

## 12. Appendices

### 12.1 Glossary

- **OAuth**: A standard protocol for authorization using third-party accounts (e.g., Google, Facebook).
- **Q&A**: A system for asking and answering questions within the platform.
- **Credit System**: A gamified incentive mechanism to encourage student participation.
- **GDPR**: General Data Protection Regulation for data privacy.

---
