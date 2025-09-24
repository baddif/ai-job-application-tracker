# REQUIREMENTS

---

## 1. Introduction
### 1.1 Purpose
The Job Application Tracker helps users record and manage their job applications, track progress across different hiring stages, and keep notes on job requirements and personal feedback.
### 1.2 Background / Motivation
As a job seeker, managing and tracking numerous job applications becomes increasingly tedious and overwhelming, particularly when pursuing remote opportunities. The modern job search often requires submitting hundreds of applications before securing a position, creating significant organizational challenges.

**Current Pain Points:**
- **Inadequate Tracking Tools**: Traditional methods like Excel spreadsheets are insufficient for managing complex application data and workflows
- **Calendar Integration Issues**: Interview schedules and important deadlines require immediate calendar entries to prevent missed opportunities
- **Information Retrieval Challenges**: Recalling specific job details, required skills, and previous interview feedback becomes difficult over time
- **Context Loss**: Critical information about job descriptions and interview history is often scattered or lost

**Project Vision:**
This project aims to create an intuitive, comprehensive system that streamlines the job application tracking process. By centralizing all job-related information and providing smart organizational features, we help job seekers maintain better control over their job search journey and improve their chances of success.
### 1.3 Scope

This system provides comprehensive job application tracking capabilities with the following core functionalities and boundaries:

**Core Capabilities:**
- **Application Management**: Record, edit, and organize job applications with detailed information
- **Progress Tracking**: Monitor application status through hiring stages (Applied, Phone Screen, Interview, Offer, Rejected)
- **Information Storage**: Maintain job requirements, descriptions, and personal notes for each application
- **Calendar Integration**: Schedule and manage interview appointments, deadlines, and important dates
- **Application Limits Tracking**: Monitor and enforce company-specific application restrictions (e.g., maximum applications per time period)
- **Multi-dimensional Views**: Organize and visualize data by skills, position types, companies, locations, and other criteria
- **Search and Filtering**: Quick access to applications based on various parameters

**Future Enhancements:**
- **AI-Powered Analysis**: Intelligent recommendations and application insights
- **Smart Resume Optimization**: AI-driven resume modifications tailored to specific positions
- **Interview Preparation**: Automated interview guides and skill development recommendations

**System Boundaries:**
- Primary focus on individual job seekers (single-user system for open-source version)
- Local deployment with optional cloud demo
- Integration capabilities with calendar systems and email platforms

**Multi-User Strategy:**
- **Open Source Version**: Single-user local deployment (Docker-based)
- **Commercial Demo**: Multi-user SaaS version for validation and potential monetization
- **Hybrid Approach**: Core functionality remains open-source, premium features (multi-user, advanced analytics) in hosted version

---

## 2. Stakeholders & User Profiles
### 2.1 Primary User

**Target Audience**: Individual job seekers actively pursuing career opportunities, particularly those applying for remote positions or conducting extensive job searches.

**User Characteristics:**
- Professionals managing high-volume job searches (typically 100-1000+ applications)
- Remote work seekers facing challenges with distributed application processes
- Career changers requiring comprehensive tracking and skill development insights

**Core Usage Scenarios:**
- **Application Volume Management**: Track extensive application portfolios with multiple interview rounds per position
- **Calendar and Schedule Management**: Create calendar events and alerts for interviews, deadlines, and follow-ups
- **Interview Preparation**: Access consolidated job requirements and skill summaries for targeted preparation
- **Progress Monitoring**: Maintain detailed records of application status across various hiring stages

**Future Usage Scenarios:**
- **Skills Gap Analysis**: Compare personal qualifications against job requirements to identify learning opportunities
- **Professional Development**: Access integrated skill development resources and course recommendations
- **Career Network Building**: Share anonymized professional profiles for recruiter and career coach connections

### 2.2 Secondary Stakeholders

**Future Multi-User Support:**
- **Career Coaches**: Guidance professionals helping clients optimize their job search strategies
- **Recruiters**: Talent acquisition specialists seeking qualified candidates through the platform
- **HR Professionals**: Company representatives managing candidate pipeline and feedback processes

---

## 3. System Overview

**Deployment options (initial plan)**: Docker-based local deployment + optional public demo.

**Technology stack (initial plan)**:

- Frontend: React + Tailwind CSS

- Backend: Node.js/NestJS

- Database: PostgreSQL

- Containerization: Docker Compose

---

## 4. Functional Requirements

(Each requirement should have an ID for traceability, e.g., FR-1, FR-2)

### 4.1 Core Features
| ID | Feature | Description | Priority |
|---|---|---|---|
| FR-1 | Job Record Management | Add, edit, delete job applications with fields: company, position, source, job link, location, salary (optional). | High |
| FR-2 | Multi-Round Progress Tracking | Track detailed hiring process with multiple rounds: each round includes type (Online Assessment, HR Screen, Technical Interview, Manager Interview, etc.), date/time, status (Scheduled, Completed, Passed, Rejected, Waiting), and personal notes/feedback. Support overall application status and round-by-round historical view. | High |
| FR-3 | Job Requirements | Save job description or key requirements. | Medium |
| FR-4 | Notes & Feedback | User can add personal notes and interview feedback. | Medium |
| FR-5 | Search & Filter | Filter by company, status, date, tags. | High |
| FR-6 | Reminders/Deadlines | Optional reminders for interviews or deadlines. | Medium |
### 4.2 Optional / Future Features
| ID | Feature | Description |
|---|---|---|
| FR-7 | Calendar View | Visualize upcoming interviews. |
| FR-8 | Email Parsing | Auto-extract job details from emails. |
| FR-9 | AI Insights | Resume-job match score, interview tips. |
| FR-10 | Multi-user Support | Enable account-based access. |

---

## 5. Non-Functional Requirements

| Category | Requirement |
|---|---|
| Performance | System should handle at least 1,000 job records without noticeable latency. |
| Security | Support HTTPS (for online demo); local Docker deployment stores data securely. |
| Usability | Intuitive UI for non-technical users with multi-round tracking interface. |
| Portability | Deployable on Linux/Mac/Windows via Docker Compose. |
| Maintainability | Clear code structure, modular components, CI/CD ready. |
| Scalability | Architecture should support future multi-user expansion. |

---

## 6. Data Model / Database Design (Initial Draft)

Entities:

User (future multi-user)

JobApplication (company, position, status, job_link, requirements, notes, dates)

Interview (date, type, result, feedback)

Provide ER Diagram placeholder.

---

## 7. System Architecture (High-Level)

Describe chosen architecture (Frontend–Backend–DB).

Show an initial architecture diagram (to be detailed in docs/architecture.md).

Mention Docker containers and network.

---

## 8. User Interface Requirements

### 8.1 Core Interface Components

**Dashboard (list view + filters)**
- Application overview table with sorting and filtering capabilities
- Quick status indicators and progress summaries

**Job detail page**
- Comprehensive application information display
- Round-by-round interview tracking interface

**Add/Edit job form**
- Streamlined data entry with validation
- Optional round tracking activation

**Calendar/Timeline view**
- Visual representation of upcoming interviews and deadlines

### 8.2 Multi-Round Progress Tracking Interface Design

**Application Status Overview:**
```
Application Status: In Progress (Round 3/4) | Expected Completion: 2024-02-05

Company: TechCorp Inc.  |  Position: Senior Software Engineer
───────────────────────────────────────────────────────────
```

**Round-by-Round Timeline:**
```
Round History:
┌─ Round 1: Online Assessment ✅ Passed (2024-01-15)
│  ├─ Duration: 90 minutes  Type: Algorithms + System Design
│  └─ Personal Notes: Challenging algorithm questions, focus on data structures and complexity analysis
│
├─ Round 2: HR Interview ✅ Passed (2024-01-22)  
│  ├─ Duration: 30 minutes  Interviewer: Sarah Chen (HR Manager)
│  └─ Personal Notes: Asked about salary expectations and work preferences, emphasized teamwork and remote work capabilities
│
├─ Round 3: Technical Interview 🕐 Awaiting Results (2024-01-29)
│  ├─ Duration: 60 minutes  Interviewer: Mike Johnson (Tech Lead)
│  └─ Personal Notes: In-depth project discussion, live coding session, interviewer was professional and friendly
│
└─ Round 4: Final Interview 📅 Scheduled (2024-02-05 14:00)
   ├─ Interviewer: David Liu (Engineering Director)
   └─ Preparation Notes: Prepare for deep project discussion, understand team culture and development plans
```

**Interactive Elements:**
- Collapsible/expandable detailed information for each round
- Status icons: ✅ Passed ❌ Rejected 🕐 Waiting 📅 Scheduled ⏰ Reminder
- Quick actions: Add round, edit notes, set reminders
- Timeline view toggle options

**User Experience Flow:**
1. **Simplified Mode**: Display only overall status, suitable for quick overview
2. **Detailed Mode**: Expand all round information, suitable for comprehensive review
3. **Edit Mode**: Allow adding/modifying round information and personal summaries

---

## 9. Deployment & Distribution

Local development setup (Node.js + Docker).

Docker Compose for one-click deployment.

Optional public demo (e.g., Render, Vercel + free DB).

---

## 10. Future Roadmap

### 10.1 Development Phases

**Phase 1: MVP (Open Source Single-User)**
- Basic CRUD operations for job applications
- Multi-round progress tracking with timeline interface
- Local Docker deployment
- Core search and filtering capabilities

**Phase 2: Enhanced Features**
- Calendar integration and reminders
- Advanced tagging and categorization system
- Import/Export functionality
- Email parsing for job details extraction

**Phase 3: Intelligence & Analytics**
- AI-powered job matching and insights
- Resume-job compatibility scoring
- Interview preparation recommendations
- Skills gap analysis and learning suggestions

**Phase 4: Commercial Expansion**
- Multi-user SaaS version development
- Advanced analytics dashboard
- Career coach collaboration features
- Enterprise-level security and compliance

### 10.2 Strategic Approach

**Dual-Track Strategy:**
- **Open Source Track**: Maintain single-user local deployment version with core functionality
- **Commercial Track**: Develop hosted multi-user SaaS for market validation and monetization
- **Community Building**: Foster open-source community while exploring commercial opportunities
- **Feature Differentiation**: Keep essential features open-source, premium features in hosted version

---

## 11. Risks & Mitigation

| Risk | Impact | Mitigation |
|---|---|---|
| Data privacy (if online demo) | High | Use demo database / anonymized data |
| User adoption | Medium | Provide clean UI, one-click deployment |
| Maintenance overhead | Medium | Modular architecture, good documentation |
| Feature complexity (multi-round tracking) | Medium | Phased implementation, user testing |
| Commercial vs Open-Source balance | Medium | Clear feature differentiation strategy |

---

## 12. References

Links to similar open-source trackers or project management tools for inspiration.