HireSphere --- AI-Powered Recruitment & Job Matching Platform
HireSphere is a full-stack recruitment platform that connects job seekers
with recruiters. Candidates can discover jobs, manage applications, and
receive skill-based job recommendations. Recruiters can manage company
profiles, publish job openings, review applicants, and track recruitment
activity.

The recommendation engine analyzes candidate skills against job
requirements and calculates a match score using Jaccard similarity and
weighted factors.
Live Links
- Frontend: https://jobhub-livid.vercel.app
- Backend API: https://jobhub-production-fda3.up.railway.app
The deployed URLs currently use the original jobhub deployment name.

Features
Candidate
- Register and log in securely.
- Search and filter jobs by keyword, location, job type, experience,
  salary, and skills.
- View job details and save jobs for later.
- Receive job recommendations with skill-match percentages.
- View skill gaps and suggested areas to improve.
- Apply for jobs and track application status.
- Upload and view a PDF resume.
- Manage profile information, including skills and career preferences.
Recruiter
- Create and manage company profiles.
- Create, update, and manage job postings.
- View applicants and inspect candidate profiles.
- Preview submitted PDF resumes.
- Update application statuses.
- View recruitment statistics through a recruiter dashboard.
Recommendation Engine
- Normalizes candidate and job skill text.
- Uses Jaccard similarity to compare skill sets.
- Calculates a weighted match score:
  - 70% skill match
  - 20% experience match
  - 10% location match
- Identifies missing skills to help candidates understand skill gaps.
Technology Stack
  Layer        Technologies
  Frontend     React 18, Vite, JavaScript, CSS
Backend      Java 21, Spring Boot 3
Security     Spring Security, JWT, BCrypt
Database     MySQL 8, Spring Data JPA, Hibernate
API          REST APIs, Axios
Deployment   Vercel, Railway, Docker
Application Architecture
React Frontend (Vercel)
        |
        | HTTP / REST API
        v
Spring Boot Backend (Railway)
        |
        +---- Spring Security + JWT
        |
        +---- Controllers / Services
        |
        +---- Spring Data JPA
                    |
                    v
                MySQL Database
Project Structure
HireSphere/
├── backend/
│   ├── src/main/java/
│   │   └── .../
│   │       ├── config/
│   │       ├── controller/
│   │       ├── dto/
│   │       ├── entity/
│   │       ├── exception/
│   │       ├── repository/
│   │       ├── security/
│   │       └── service/
│   ├── src/main/resources/
│   ├── pom.xml
│   └── Dockerfile
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── context/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.jsx
│   │   └── index.css
│   ├── package.json
│   └── vercel.json
│
└── README.md
Getting Started
Prerequisites
Make sure you have the following installed:
- Java 21
- Maven (or use the included Maven Wrapper)
- Node.js and npm
- MySQL 8
1. Clone the repository
git clone <your-repository-url>
cd <repository-folder>
2. Configure the database
Create a MySQL database:
CREATE DATABASE jobhub_db;
Configure the database URL, username, and password in:
backend/src/main/resources/application.properties
Use environment variables or local configuration for credentials. Do not
commit database passwords, JWT secrets, or other sensitive values to
Git.
3. Run the backend
cd backend
./mvnw spring-boot:run
On Windows:
mvnw.cmd spring-boot:run
The backend runs on http://localhost:8080 by default.
4. Run the frontend
Open another terminal:
cd frontend
npm install
npm run dev
Vite will display the local frontend URL in the terminal, usually
http://localhost:5173.
Key API Routes
  Module            Method   Endpoint                          Access
  Authentication    POST     /api/auth/register              Public
Authentication    POST     /api/auth/login                 Public
Jobs              GET      /api/jobs/search                Public
Jobs              GET      /api/jobs/latest                Public
Jobs              GET      /api/jobs/{id}                  Public
Jobs              POST     /api/jobs                       Recruiter
Recommendations   GET      /api/ai/recommendations         Candidate
Companies         GET      /api/companies/search           Public
Applications      POST     /api/applications               Candidate
Applications      GET      /api/applications/my            Candidate
Applications      PUT      /api/applications/{id}/status   Recruiter
Saved Jobs        POST     /api/saved-jobs/{jobId}         Candidate
Saved Jobs        GET      /api/saved-jobs                 Candidate
Dashboard         GET      /api/dashboard/candidate        Candidate
Dashboard         GET      /api/dashboard/recruiter        Recruiter
Application Status Workflow
APPLIED
   |
   v
REVIEWING
   |
   v
SHORTLISTED
   |
   +----> SELECTED
   |
   +----> REJECTED
Security
- Stateless authentication using JSON Web Tokens (JWT).
- Password hashing using BCrypt.
- Role-based access for candidate and recruiter operations.
- Protected API endpoints for authenticated actions.
Future Enhancements
- Email notifications for application status changes.
- More advanced recommendation and ranking methods.
- Interview scheduling and recruiter-candidate messaging.
- Automated resume parsing and skill extraction.
