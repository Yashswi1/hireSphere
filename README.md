# HireSphere – Full-Stack Recruitment & Career Management Platform

HireSphere is a full-stack recruitment platform designed to connect job seekers with recruiters through a streamlined and efficient hiring process. The application enables candidates to discover opportunities, apply for jobs, and track their applications, while recruiters can manage job postings and evaluate applicants.

Built using **Java, Spring Boot, React, Hibernate, and MySQL**, HireSphere demonstrates modern full-stack development practices, RESTful API design, secure authentication, and database management.

## 🚀 Features

### 👤 Job Seeker
- User registration and secure login
- Browse and search job opportunities
- Filter jobs by location, skills, and employment type
- View detailed job descriptions
- Apply for jobs and upload resumes
- Track application status
- Manage personal profile and resume

### 🏢 Recruiter
- Recruiter registration and authentication
- Create, update, and delete job postings
- View applicants for posted jobs
- Review candidate profiles and resumes
- Update application statuses
- Manage recruitment activities

### 🛡️ Admin
- Manage users and recruiters
- Monitor job postings
- Maintain platform data and activity

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Frontend | React.js, JavaScript, HTML, CSS |
| Backend | Java, Spring Boot |
| ORM | Hibernate, Spring Data JPA |
| Database | MySQL |
| Security | Spring Security, JWT |
| API | RESTful APIs |
| Build Tool | Maven |
| Testing | JUnit, Mockito |
| Development Tools | Git, GitHub, Postman |

## 🏗️ System Architecture

```text
             React Frontend
                   |
             REST API Calls
                   |
          Spring Boot Backend
                   |
        ----------------------
        |          |         |
    Controllers  Services  Security
                   |
             Spring Data JPA
                   |
                Hibernate
                   |
               MySQL DB
```

## 📂 Project Structure

```text
HireSphere/
├── frontend/
│   ├── public/
│   └── src/
│       ├── components/
│       ├── pages/
│       ├── services/
│       ├── hooks/
│       └── App.jsx
│
├── backend/
│   └── src/main/
│       ├── java/
│       │   └── com/hiresphere/
│       │       ├── controller/
│       │       ├── service/
│       │       ├── repository/
│       │       ├── entity/
│       │       ├── dto/
│       │       ├── config/
│       │       └── security/
│       └── resources/
│           └── application.properties
│
├── .gitignore
└── README.md
```

## ⚙️ Installation & Setup

### Prerequisites
- Java 17 or later
- Node.js and npm
- MySQL
- Maven
