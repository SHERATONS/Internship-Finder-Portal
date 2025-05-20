# Internship-Finder-Portal-Backend
This project is for my practical back-end skills. It is a backend system that connects students and recruiters, allowing internships to be posted, applied for, and tracked, with robust role management, authentication, and notifications.

Requirement
✅ Project: Internship Finder Portal
🎯 Goal
Build a backend system that connects students and recruiters, allowing internships to be posted, applied for, and tracked, with robust role management, authentication, and notifications.

📁 High-Level Modules
Authentication & Authorization

User Management (Student, Recruiter, Admin)

Internship Management

Application Management

Interview Scheduling

Notification System

Admin Dashboard

(Optional) Resume Matching Engine

🧠 Entities & Relationships (ERD Summary)
Entities:
User

id, email, password, role (STUDENT, RECRUITER, ADMIN)

StudentProfile

user_id (FK), name, university, major, resume_url, skills

RecruiterProfile

user_id (FK), company_name, contact_info, description

Internship

id, recruiter_id (FK), title, description, location, duration, skills_required, created_at

Application

id, student_id (FK), internship_id (FK), status (APPLIED, SHORTLISTED, INTERVIEW, REJECTED, HIRED), applied_at

Interview

id, application_id (FK), scheduled_at, link, notes

Notification

id, user_id (FK), content, is_read, created_at

🔐 Authentication
JWT-based authentication

Role-based authorization (Spring Security)

Password hashing using BCrypt

User registration & login endpoints

📦 API Structure (Sample Routes)
/auth
POST /register → Register (Student or Recruiter)

POST /login → Login and receive JWT

/students
GET /profile → Get own student profile

POST /profile → Create/Update profile

GET /applications → View application status

POST /apply/{internshipId} → Apply for internship

/recruiters
GET /profile → Get own recruiter profile

POST /profile → Create/Update profile

POST /internships → Create internship

GET /internships → List posted internships

GET /applicants/{internshipId} → View applicants

POST /interview/{applicationId} → Schedule interview

/admin
GET /users → List all users

DELETE /user/{id} → Ban/Delete user

GET /stats → General stats (applicant count, hires, etc.)

/notifications
GET / → List notifications

POST /read/{id} → Mark as read

🗃️ Database: PostgreSQL
Use JPA/Hibernate to define relationships and handle persistence.

🛠️ Tech Stack
Java 17

Spring Boot

Spring Security

Spring Data JPA

PostgreSQL

JWT for auth

Lombok for cleaner code

Swagger for API documentation

JUnit + Mockito for testing

Docker (optional)

🧪 Testing
Unit tests for services (e.g., user registration, applying to internships)

Integration tests for core endpoints

Postman collection for API testing