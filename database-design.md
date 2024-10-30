```mermaid
erDiagram

    %% Define Entities
    User {
        Int id PK
        String name
        String email UNIQUE
        String password
        Role role
        DateTime createdAt
        DateTime updatedAt
    }

    Course erDiagram

    %% Define Entities
    User {
        Int id PK
        String name
        String email UNIQUE
        String password
        Role role
        DateTime createdAt
        DateTime updatedAt
    }

    Course {
        Int id PK
        String title
        String description
        Float rating
        DateTime createdAt
        DateTime updatedAt
    }

    Lesson {
        Int id PK
        String title
        String content
        String videoUrl
        Int order
        DateTime createdAt
        DateTime updatedAt
    }

    Enrollment {
        Int id PK
        AccessType accessType
        String status
        DateTime createdAt
        DateTime updatedAt
    }

    Progress {
        Int id PK
        Boolean lessonCompletion
        Json quizResults
        FlaggedStatus flaggedStatus
        DateTime createdAt
        DateTime updatedAt
    }

    Group {
        Int id PK
        GroupType groupType
        DateTime createdAt
        DateTime updatedAt
    }

    GroupMember {
        Int id PK
    }

    CreditPoint {
        Int id PK
        Int pointsTotal
        Json pointsBreakdown
        Json badgesEarned
        DateTime createdAt
        DateTime updatedAt
    }

    Rating {
        Int id PK
        Int rating
        String review
        DateTime createdAt
        DateTime updatedAt
    }

    Question {
        Int id PK
        String content
        Float priorityScore
        Int upvoteCount
        DateTime createdAt
        DateTime updatedAt
    }

    QuestionUpvote {
        Int id PK
    }

    Certificate {
        Int id PK
        AchievementType achievement
        DateTime dateIssued
    }

    Revenue {
        Int id PK
        Float earnedAmount
        Int studentEnrollment
        DateTime createdAt
        DateTime updatedAt
    }

    %% Define Relationships
    User ||--o{ Course : "teacherCourses"
    User ||--o{ Enrollment : enrollments
    User ||--o{ Progress : progresses
    User ||--|| CreditPoint : creditPoints
    User ||--o{ Rating : ratings
    User ||--o{ Question : questions
    User ||--o{ GroupMember : groupMembers
    User ||--o{ Certificate : certificates
    User ||--o{ Revenue : revenues
    User ||--o{ QuestionUpvote : upvotes

    Course }o--o{ Enrollment : enrollments
    Course ||--o{ Progress : progresses
    Course ||--o{ Rating : ratings
    Course ||--o{ Lesson : lessons
    Course ||--o{ Certificate : certificates
    Course ||--o{ Revenue : revenues

    Lesson ||--o{ Progress : progresses
    Lesson ||--o{ Question : questions

    Enrollment }o--|| User : student
    Enrollment }o--|| Course : course

    Progress }o--|| User : student
    Progress }o--|| Course : course
    Progress }o--|| Lesson : lesson

    Group ||--o{ GroupMember : groupMembers
    GroupMember }o--|| Group : group
    GroupMember }o--|| User : student

    CreditPoint ||--|| User : student

    Rating }o--|| User : student
    Rating }o--|| Course : course

    Question }o--|| User : student
    Question }o--|| Lesson : lesson
    Question ||--o{ QuestionUpvote : upvotes

    QuestionUpvote }o--|| Question : question
    QuestionUpvote }o--|| User : user

    Certificate }o--|| User : student
    Certificate }o--|| Course : course

    Revenue }o--|| User : teacher
    Revenue }o--|| Course : course

{
        Int id PK
        String title
        String description
        Float rating
        DateTime createdAt
        DateTime updatedAt
    }

    Lesson {
        Int id PK
        String title
        String content
        String videoUrl
        Int order
        DateTime createdAt
        DateTime updatedAt
    }

    Enrollment {
        Int id PK
        AccessType accessType
        String status
        DateTime createdAt
        DateTime updatedAt
    }

    Progress {
        Int id PK
        Boolean lessonCompletion
        Json quizResults
        FlaggedStatus flaggedStatus
        DateTime createdAt
        DateTime updatedAt
    }

    Group {
        Int id PK
        GroupType groupType
        DateTime createdAt
        DateTime updatedAt
    }

    GroupMember {
        Int id PK
    }

    CreditPoint {
        Int id PK
        Int pointsTotal
        Json pointsBreakdown
        Json badgesEarned
        DateTime createdAt
        DateTime updatedAt
    }

    Rating {
        Int id PK
        Int rating
        String review
        DateTime createdAt
        DateTime updatedAt
    }

    Question {
        Int id PK
        String content
        Float priorityScore
        Int upvoteCount
        DateTime createdAt
        DateTime updatedAt
    }

    QuestionUpvote {
        Int id PK
    }

    Certificate {
        Int id PK
        AchievementType achievement
        DateTime dateIssued
    }

    Revenue {
        Int id PK
        Float earnedAmount
        Int studentEnrollment
        DateTime createdAt
        DateTime updatedAt
    }

    %% Define Relationships
    User ||--o{ Course : "teacherCourses"
    User ||--o{ Enrollment : enrollments
    User ||--o{ Progress : progresses
    User ||--|| CreditPoint : creditPoints
    User ||--o{ Rating : ratings
    User ||--o{ Question : questions
    User ||--o{ GroupMember : groupMembers
    User ||--o{ Certificate : certificates
    User ||--o{ Revenue : revenues
    User ||--o{ QuestionUpvote : upvotes

    Course }o--o{ Enrollment : enrollments
    Course ||--o{ Progress : progresses
    Course ||--o{ Rating : ratings
    Course ||--o{ Lesson : lessons
    Course ||--o{ Certificate : certificates
    Course ||--o{ Revenue : revenues

    Lesson ||--o{ Progress : progresses
    Lesson ||--o{ Question : questions

    Enrollment }o--|| User : student
    Enrollment }o--|| Course : course

    Progress }o--|| User : student
    Progress }o--|| Course : course
    Progress }o--|| Lesson : lesson

    Group ||--o{ GroupMember : groupMembers
    GroupMember }o--|| Group : group
    GroupMember }o--|| User : student

    CreditPoint ||--|| User : student

    Rating }o--|| User : student
    Rating }o--|| Course : course

    Question }o--|| User : student
    Question }o--|| Lesson : lesson
    Question ||--o{ QuestionUpvote : upvotes

    QuestionUpvote }o--|| Question : question
    QuestionUpvote }o--|| User : user

    Certificate }o--|| User : student
    Certificate }o--|| Course : course

    Revenue }o--|| User : teacher
    Revenue }o--|| Course : course

```
