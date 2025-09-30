# AI Job Application Tracker

A Docker-based system for job seekers to track the application process with AI-powered skills extraction.

> 🚧 **Under Development** - Currently building requirements and architecture design.

## 🏗️ System Architecture

```mermaid
flowchart TB
    User[👤 Job Seeker] --> Browser[🌐 Web Browser]
    Browser --> Frontend[📱 React Frontend<br/>localhost:3000]
    
    subgraph "Docker Compose Environment"
        Frontend <--> Backend[⚙️ Node.js/NestJS Backend<br/>Port 8000]
        Backend <--> DB[(🗄️ PostgreSQL Database<br/>Port 5432)]
    end
    
    style Frontend fill:#f3e5f5,color:#000000
    style Backend fill:#e8f5e8,color:#000000
    style DB fill:#fff3e0,color:#000000
    style User color:#ffffff
    style Browser color:#ffffff
```

## ✨ Key Features

- **📊 Multi-Round Interview Tracking**: Detailed hiring process timeline with notes
- **🤖 AI Skills Extraction**: Automatically identify required skills from job descriptions  
- **🔒 Privacy-First**: Local deployment with Docker - your data stays on your machine
- **📅 Calendar Integration**: Schedule interviews and set reminders
- **🔍 Smart Search & Filter**: Find applications by company, status, skills, and more

## 🎯 Core Capabilities

```mermaid
mindmap
  root((Job Application Tracker))
    Application Management
      Add/Edit/Delete Jobs
      Company Information
      Position Details
      Salary Tracking
    Progress Tracking
      Applied
      Phone Screen
      Multiple Interview Rounds
      Offer/Rejection
      Personal Notes
    AI Features
      Skills Extraction
      Job Requirements Analysis
      Technology Stack Detection
    Organization
      Search & Filter
      Tags & Categories
      Calendar Integration
      Reminders
```

## 🔧 Backend Architecture

```mermaid
flowchart TD
    API[🌐 REST API Layer] --> Auth[🔐 Authentication]
    API --> JobController[📋 Job Controller]
    API --> InterviewController[📅 Interview Controller]
    
    JobController --> JobService[📊 Job Service]
    InterviewController --> InterviewService[🎯 Interview Service]
    
    JobService --> AI[🤖 AI Skills Extractor]
    JobService --> DB[🗄️ Database Layer]
    InterviewService --> DB
    
    subgraph "AI Module"
        AI --> NLP[📝 Natural.js NLP]
        AI --> SkillsDB[🏷️ Skills Database]
        AI --> Patterns[🔍 Pattern Matching]
    end
    
    style AI fill:#e3f2fd
    style NLP fill:#f1f8e9
    style SkillsDB fill:#f1f8e9
    style Patterns fill:#f1f8e9
```

## 🚀 Technology Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Frontend** | React + Tailwind CSS | User interface and experience |
| **Backend** | Node.js/NestJS | API and business logic |
| **Database** | PostgreSQL | Data persistence |
| **AI Engine** | Natural.js + future GPT integration | Skills extraction and analysis |
| **Deployment** | Docker Compose | Easy local setup |

## 📚 Documentation

| Document | Description |
|----------|-------------|
| [📋 Requirements](docs/REQUIREMENTS.md) | Detailed project requirements and specifications |
| [🏗️ Architecture](docs/architecture.md) | System design and technical architecture *(Coming Soon)* |
| [🚀 Getting Started](docs/getting-started.md) | Installation and setup guide *(Coming Soon)* |
| [🤝 Contributing](CONTRIBUTING.md) | How to contribute to the project *(Coming Soon)* |

## 🗺️ Development Roadmap

```mermaid
timeline
    title Development Phases
    
    Phase 1 : MVP (Q4 2025)
           : Core CRUD Operations
           : Multi-round Tracking
           : AI Skills Extraction
           : Docker Deployment
    
    Phase 2 : Enhanced Features (Q1 2026)
           : Calendar Integration
           : Advanced Search
           : Email Parsing
           : Import/Export
    
    Phase 3 : AI Intelligence (Q2 2026)
           : Smart Recommendations
           : Company Research
           : Interview Preparation
           : Resume Matching
    
    Phase 4 : Commercial Expansion (Q3 2026)
           : Multi-user SaaS
           : Advanced Analytics
           : Enterprise Features
           : Market Intelligence
```

## 🎯 Project Vision

As a job seeker, managing hundreds of applications becomes overwhelming. Traditional tools like Excel spreadsheets are inadequate for complex hiring workflows. This project aims to create an intuitive system that:

- **Centralizes** all job application information
- **Tracks** multi-round interview processes  
- **Extracts** key requirements using AI
- **Protects** your privacy with local deployment

[📋 Read full project background](docs/REQUIREMENTS.md#12-background--motivation)

## 🔄 Current Status

- ✅ Requirements documentation complete
- 🚧 Architecture design in progress  
- ⏳ Frontend development starting soon
- ⏳ Backend API design
- ⏳ Database schema design

## 🤝 Contributing

This is an open-source project and contributions are welcome! Whether you're interested in:

- 🎨 **Frontend Development** (React/TypeScript)
- ⚙️ **Backend Development** (Node.js/NestJS) 
- 🤖 **AI Integration** (NLP/Skills Extraction)
- 📖 **Documentation** (Technical writing)
- 🧪 **Testing** (Unit/Integration tests)

[📋 View detailed feature requirements](docs/REQUIREMENTS.md#4-functional-requirements)

## 📄 License

MIT License - feel free to use this project for personal or commercial purposes.

---

**🚀 Star this repo if you find it useful!** Your support helps prioritize development.
