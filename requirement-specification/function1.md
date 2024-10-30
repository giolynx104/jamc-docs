# **Function 1: User Registration and Onboarding**

**Objective**: Enable both teachers and students to register and create accounts, allowing them to access the platform's features.

## **Detailed Description**

### **For Teachers**

- **Registration Process**:
  - Teachers can register using credentials (email and password) or OAuth options (Google, Facebook).
  - More information required including full name, email, password, and optionally, school affiliation or verification documents.
  - Password must meet security requirements (e.g., minimum length, complexity).

- **Account Activation**:
  - Email verification to confirm the teacher's email address or the OAuth services must send an email about the permissions.
    - I'm not sure how OAuth services handle this yet
       - Google: consent screen
    - How to send an email after registration? I guess there is a service for that but I haven't checked any of them yet.
  - Optional: Manual approval by an administrator to verify teacher credentials.
    - I wonder about the administrator role here because we may need to build a lot of things for this administration. I guess currently we will opt this out

- **Post-Registration Actions**:
  - Onboarding flow including:
    - Welcome page: greet the user and explain what to do next
    - Confirm the user's role (if they registered via OAuth)
    - Collect additional information 
  - Create a class and receive a unique class code.
    - How should we generate a unique class code?
  - Set up their profile, including a profile picture, bio, and teaching subjects.
    - How do we handle the profile picture? New URL, new image bytes is the best option for the following questions.
      - Whether to save the uploaded images (previous profile picture)
      - How do we handle the avatar update from user?
  - Access the course creation tools to start building courses.

### **For Students**

- **Registration Process**:
  - Students can register using their email address or social media accounts (e.g., Google, Facebook).
  - Required information includes full name, email, password, and optionally, profile picture or avatar.
  - Password must meet security requirements.

- **Account Activation**:
  - Email verification to confirm the student's email address.

- **Class Enrollment**:
  - Enter the class code provided by their teacher to request enrollment.
  - The system notifies the teacher of the enrollment request.
  - Students can view the status of their enrollment requests.

- **Post-Enrollment Actions**:
  - Access course materials upon teacher approval.
  - Set up their profile and learning preferences.

## **Functional Requirements**

### **Registration Forms**

- **Common Fields**:
  - `Full Name` (string, required)
  - `Email Address` (string, required, unique)
  - `Password` (string, required, encrypted)
  - `Confirm Password` (string, required, must match `Password`)
  - `User Role` selection (enum: Student, Teacher)
  - Accept Terms and Conditions (checkbox, required)

- **Additional Fields for Teachers**:
  - `School Affiliation` (string, optional)
  - `Verification Documents` (file upload, optional)

### **Email Verification**

- Send a verification email upon registration.
- The email contains a secure, time-limited activation link.
- Account remains inactive until email is verified.

### **Authentication**

- Secure login with email and password.
- Implement password hashing and salting (e.g., bcrypt).
- Option to reset password via email.
- Account lockout after multiple failed login attempts (e.g., 5 attempts).

### **Class Code Enrollment (Students)**

- Input field to enter a class code on the student dashboard.
- Validate class code format and existence.
- Notify the teacher of the enrollment request.
- Display pending enrollment requests to the student.

### **Teacher Approval Interface**

- Dashboard displaying pending enrollment requests.
- Options to approve or deny each request.
- Bulk actions to approve or deny multiple requests.
- Automatic notification to students upon decision.

### **Profile Completion**

- **Profile Picture**: display default avatar and handle avatar uploads from user properly
- **Profile Completion**: display profile completion status and prompt to complete profile for teachers
## **Non-Functional Requirements**

- **Security**:
  - SSL/TLS encryption for all data in transit.
  - Protect against common web vulnerabilities (OWASP Top Ten).
  - Secure storage of user data and compliance with data protection regulations.

- **Usability**:
  - Intuitive and user-friendly interface.
  - Responsive design for desktop and mobile devices.
  - Accessibility compliance (e.g., WCAG 2.1 AA).

- **Performance**:
  - Fast loading times for registration and login pages.
  - Efficient handling of form submissions and database transactions.

- **Scalability**:
  - Support for increasing numbers of users without degradation of performance.
  - Efficient database indexing and query optimization.

## **Data Fields for Database**

### **User Table**

- `id` (Integer, Primary Key, Auto-increment)
- `full_name` (String, Not Null)
- `email` (String, Not Null, Unique)
- `password_hash` (String, Not Null)
- `role` (Enum: STUDENT, TEACHER)
- `profile_picture_url` (String, Optional)
- `email_verified` (Boolean, Default: False)
- `created_at` (Timestamp)
- `updated_at` (Timestamp)
- `last_login_at` (Timestamp, Optional)

### **Teacher Details Table** (if needed)

- `user_id` (Foreign Key to User.id, Primary Key)
- `school_affiliation` (String, Optional)
- `verification_status` (Enum: PENDING, VERIFIED, REJECTED)
- `verification_documents_url` (String, Optional)
- `bio` (Text, Optional)

### **Class Table**

- `id` (Integer, Primary Key, Auto-increment)
- `teacher_id` (Foreign Key to User.id)
- `class_code` (String, Unique, Not Null)
- `class_name` (String, Not Null)
- `description` (Text, Optional)
- `created_at` (Timestamp)
- `updated_at` (Timestamp)

### **Enrollment Request Table**

- `id` (Integer, Primary Key, Auto-increment)
- `student_id` (Foreign Key to User.id)
- `class_id` (Foreign Key to Class.id)
- `status` (Enum: PENDING, APPROVED, DENIED)
- `requested_at` (Timestamp)
- `responded_at` (Timestamp, Optional)

### **Additional Tables**

- **Email Verification Tokens**:
  - `user_id` (Foreign Key to User.id)
  - `token` (String, Unique)
  - `expires_at` (Timestamp)
- **Password Reset Tokens**:
  - `user_id` (Foreign Key to User.id)
  - `token` (String, Unique)
  - `expires_at` (Timestamp)

## **User Interface (UI) Considerations**

### **Registration Page**

- **Separate Forms or Tabs**:
  - Clearly distinguish between Student and Teacher registration paths.
- **Form Validation**:
  - Real-time validation for email format, password strength, required fields.
- **Security Indicators**:
  - Show password strength meter.
- **Terms and Conditions**:
  - Link to policies with checkbox for acceptance.

### **Login Page**

- **Fields**:
  - Email address and password.
- **Features**:
  - "Remember me" option.
  - "Forgot password?" link leading to password recovery.
- **Error Handling**:
  - Clear messages for incorrect credentials or unverified email.

### **Student Dashboard**

- **First-Time Use**:
  - Prompt to enter a class code if not enrolled in any classes.
- **Enrollment Status**:
  - Display pending, approved, and denied class enrollment requests.
- **Navigation**:
  - Access to profile settings, enrolled classes, and support.

### **Teacher Dashboard**

- **Class Management**:
  - Create new classes with class codes.
  - View and manage existing classes.
- **Enrollment Requests**:
  - Notification center for pending student requests.
- **Profile Completion**:
  - Prompt to complete profile and verification (if applicable).

## **API Endpoints**

### **Authentication**

- `POST /api/auth/register` - Register a new user.
- `POST /api/auth/login` - Authenticate user and create session.
- `POST /api/auth/logout` - Invalidate user session.
- `POST /api/auth/verify-email` - Verify email with token.
- `POST /api/auth/reset-password` - Request password reset.
- `POST /api/auth/update-password` - Update password with reset token.

### **Teacher Actions**

- `POST /api/teachers/classes` - Create a new class.
- `GET /api/teachers/classes` - Retrieve list of classes.
- `GET /api/teachers/classes/:classId/requests` - Get enrollment requests.
- `POST /api/teachers/classes/:classId/requests/:requestId/approve` - Approve request.
- `POST /api/teachers/classes/:classId/requests/:requestId/deny` - Deny request.

### **Student Actions**

- `POST /api/students/classes/enroll` - Request enrollment in a class.
- `GET /api/students/classes` - Get list of enrolled classes.

## **Business Logic**

- **Email Verification Required**:
  - Users must verify their email before accessing certain features.
- **Unique Class Codes**:
  - Generate secure, unique class codes for each class.
- **Enrollment Control**:
  - Teachers have full control over which students join their classes.
- **Role-Based Permissions**:
  - Enforce access controls based on user roles throughout the application.

## **Security Considerations**

- **Data Protection**:
  - Comply with GDPR or relevant data protection laws.
- **Input Validation**:
  - Sanitize all user inputs to prevent SQL injection, XSS attacks.
- **Session Management**:
  - Use secure cookies with appropriate flags (HttpOnly, Secure).

## **Error Handling**

- Provide user-friendly error messages.
- Log errors server-side for troubleshooting without exposing sensitive information to the user.

## **Performance Considerations**

- **Caching**:
  - Implement caching strategies for static resources.
- **Database Optimization**:
  - Use indexes on frequently queried fields (e.g., email, class_code).
- **Load Testing**:
  - Test system under expected load conditions to ensure responsiveness.