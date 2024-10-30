# Function 3: Classes

## User Stories

### Teacher Stories:

1. As a teacher, I want to create a new class with necessary details (name, description, schedule, etc.) so that students can join and access materials.
2. As a teacher, I want to upload class materials (documents, videos, resources) to provide content for students.
3. As a teacher, I want to manage enrolled students (view list, remove, etc.) to ensure the right participants are in the class.
4. As a teacher, I want to post announcements to keep students informed about updates or changes.
5. As a teacher, I want to integrate the class with the public discussion forum for course-related communication.
6. As a teacher, I want to set up quizzes or assignments and receive submissions from students.
7. As a teacher, I want to track student attendance and performance data to monitor engagement and progress.

### Student Stories:

1. As a student, I want to browse and join classes to access materials relevant to my school curriculum.
2. As a student, I want to view class schedules so that I can attend sessions on time.
3. As a student, I want to access class materials (documents, resources) for study.
4. As a student, I want to participate in discussions to engage with the teacher and peers.
5. As a student, I want to submit assignments or take quizzes as part of class requirements.
6. As a student, I want to receive notifications for updates, new materials, or upcoming deadlines.

## Feature Prioritization

### Must-Have (MVP):

- Class creation by teachers with essential information.
- Real-time scheduling and alignment with Vietnamese high school curriculum.
- Upload and access to class materials.
- Integration with the public discussion forum.
- Basic quiz/assignment feature for submission and grading.
- Notifications for class updates, new materials, and deadlines.

### Nice-to-Have (Future Enhancements):

- In-class messaging (future discussion on apps integration).
- Advanced analytics and data visualization.
- Detailed admin roles and permissions.
- More sophisticated assessment tools and gradebooks.

## Workflow

### Class Creation:

1. Teachers log in → Navigate to "Create Class" → Fill in class information (name, description, schedule, materials) → Submit.

### Class Management:

1. Teachers manage enrolled students → Add/Remove students as needed → Post announcements or updates.

### Material Upload:

1. Teachers upload documents or videos → Students access materials via the class page.

### Discussion Integration:

1. Link public discussion forum to specific classes → Students and teachers participate in discussions.

### Assignments/Quizzes:

1. Teachers create assignments/quizzes → Students submit → Teachers review and provide feedback.

### Notifications:

1. System sends notifications to students for new materials, deadlines, and announcements.

## Routing

/classes → Class Dashboard
/classes/
→ Class Detail Page
/classes/
/materials → Class Materials
/classes/
/discussions → Class-specific discussions
/classes/
/assignments → Assignment/Quiz Management
/notifications → Notification Center
