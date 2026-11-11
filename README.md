# 🚀 OpenScout – AI-Powered Open Source Project Finder

<p align="center">
  <a href="https://openscout-ai-dun.vercel.app/">
    <img src="https://img.shields.io/badge/🚀_Live_Demo-Visit_OpenScout-brightgreen?style=for-the-badge" alt="Live Demo"/>
  </a>
  <a href="https://github.com/sujith2359/open-source-project-finder">
    <img src="https://img.shields.io/badge/GitHub-Source_Code-black?style=for-the-badge&logo=github" alt="GitHub"/>
  </a>
</p>

OpenScout is an AI-powered open-source project discovery platform that helps developers find, evaluate, compare, and understand GitHub repositories using natural-language queries.

Instead of manually searching through hundreds of repositories, developers can describe their requirements in simple English and receive relevant project recommendations powered by AI, semantic search, and Retrieval-Augmented Generation (RAG).

## 🌐 Live Demo

**Try OpenScout here:**

https://openscout-ai-dun.vercel.app/

**GitHub Repository:**

https://github.com/sujith2359/open-source-project-finder

---

## 📌 1. Project Introduction

Finding the right open-source library, framework, or starter template can take hours of searching through GitHub repositories, documentation, star counts, and outdated issues.

Traditional repository searches often fail to understand complex requirements involving multiple technologies, domains, and developer experience levels.

OpenScout addresses this problem through AI-powered repository discovery.

### Example User Query

"I want to build an AI healthcare chatbot using Python, FastAPI, and React. I am a beginner and prefer repositories with good documentation."

OpenScout analyzes the user's requirements, extracts technical constraints using Mistral AI, searches GitHub repositories, performs semantic similarity matching, and recommends relevant projects.

It also provides an AI-powered repository chatbot that helps users explore repository documentation and code through conversational questions.

## 🎯 2. Project Objectives

- **Natural Language Query Understanding:** Convert user queries into structured project requirements.
- **AI-Powered Requirement Extraction:** Identify programming languages, frameworks, domains, experience levels, and license preferences.
- **Live GitHub Search:** Discover repositories using the GitHub REST API.
- **Semantic Repository Matching:** Find relevant projects using Sentence Transformers and pgvector.
- **Intelligent Ranking:** Rank repositories based on semantic relevance, documentation quality, and repository health.
- **AI-Generated Explanations:** Explain why a repository matches the user's requirements.
- **Repository Comparison:** Compare multiple repositories based on architecture, activity, and community support.
- **RAG-Based Repository Chatbot:** Ask questions about indexed repository documentation and codebase content.

## 🛠️ 3. Technology Stack

### Frontend
- React.js 19
- TypeScript
- Vite 8
- Tailwind CSS 4

### Backend
- Python
- FastAPI
- Pydantic
- Pydantic Settings
- Uvicorn

### AI and Machine Learning
- Mistral AI API – Natural-language understanding and AI-generated responses.
- Mistral Small Latest – Primary language model.
- Sentence Transformers – Semantic embeddings.
- `sentence-transformers/all-MiniLM-L6-v2` – Embedding model with 384 dimensions.
- Retrieval-Augmented Generation (RAG) – Repository question answering.

### Database and Storage
- PostgreSQL
- pgvector
- SQLAlchemy
- Alembic

### External Integration
- GitHub REST API v3
- HTTPX

### Deployment and Development
- GitHub
- Vercel – Frontend hosting.
- Render – Backend and database deployment option.
- Docker
- GitHub Actions

## 🏗️ 4. System Architecture

OpenScout follows a modular frontend-backend architecture.

### High-Level Workflow

1. The user enters a natural-language project requirement.
2. React sends the query to the FastAPI backend.
3. Mistral AI extracts structured requirements.
4. The backend searches live GitHub repositories.
5. Sentence Transformers generates semantic embeddings.
6. pgvector performs semantic similarity matching.
7. The system ranks and filters relevant repositories.
8. AI generates explanations for recommended projects.
9. Repository documentation can be indexed for RAG-based question answering.
10. The frontend displays project recommendations and chatbot responses.

### Architecture Components

| Component | Responsibility |
|---|---|
| React + TypeScript | User interface |
| FastAPI | Backend API and business logic |
| Mistral AI | Query understanding and language generation |
| GitHub REST API | Live repository discovery |
| Sentence Transformers | Text embeddings |
| PostgreSQL + pgvector | Relational and vector storage |
| RAG | Context-based repository question answering |
| Vercel | Frontend deployment |

## 📂 5. Project Directory Structure

```text
OpenScout/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── types/
│   │   ├── assets/
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── public/
│   ├── package.json
│   └── .env.example
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── core/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   └── main.py
│   ├── tests/
│   ├── requirements.txt
│   └── .env.example
│
├── docs/
│   └── ARCHITECTURE.md
│
├── .gitignore
└── README.md
```

## ⚙️ 6. Installation and Setup

### Prerequisites

Install the following:

- Node.js 18 or later
- Python 3.10 or later
- PostgreSQL with pgvector
- Git
- Docker (for the configured database setup)

### Step 1: Clone the Repository

```bash
git clone https://github.com/sujith2359/open-source-project-finder.git

cd open-source-project-finder
```

### Step 2: Setup Frontend

```bash
cd frontend

npm install

npm run dev
```

Frontend development URL:

```text
http://localhost:5173
```

### Step 3: Setup Backend

Open another terminal:

```bash
cd backend

python -m venv .venv
```

Activate the virtual environment.

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Linux/macOS:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start FastAPI:

```bash
uvicorn app.main:app --app-dir backend --reload --port 8000
```

Backend URL:

```text
http://localhost:8000
```

Swagger API documentation:

```text
http://localhost:8000/docs
```

### Step 4: Setup Database

From the project root:

```bash
docker compose up -d
```

Run database migrations:

```bash
cd backend

alembic upgrade head
```

Ensure that your PostgreSQL database has the pgvector extension enabled and the database connection is correctly configured.

## 🔐 7. Environment Variables

Create your local environment files using the provided examples.

### Backend Configuration

File: `backend/.env`

| Variable | Description |
|---|---|
| FRONTEND_URL | Frontend origin allowed by CORS |
| ALLOWED_ORIGINS | Additional allowed frontend origins |
| MISTRAL_API_KEY | Mistral API key |
| MISTRAL_MODEL | Mistral model identifier |
| GITHUB_TOKEN | Optional GitHub personal access token |
| DATABASE_URL | PostgreSQL connection URL |
| EMBEDDING_MODEL | Sentence Transformers model |
| EMBEDDING_DIMENSION | Embedding dimension (384) |

Example model configuration:

```env
MISTRAL_MODEL=mistral-small-latest
EMBEDDING_MODEL=sentence-transformers/all-MiniLM-L6-v2
EMBEDDING_DIMENSION=384
```

### Frontend Configuration

File: `frontend/.env`

```env
VITE_API_BASE_URL=http://localhost:8000
```

For production, configure this variable with your deployed backend API URL.

**Security:** Never expose Mistral API keys, GitHub tokens, or database credentials in frontend code or public repositories.

## 🔌 8. Important API Endpoints

The backend provides API endpoints for repository discovery, semantic search, indexing, and RAG-based conversations.

| Endpoint | Method | Purpose |
|---|---|---|
| `/` | GET | Root endpoint |
| `/api/health` | GET | Health check |
| `/api/v1/understand-query` | POST | AI query understanding |
| `/api/v1/search/semantic-search` | POST | Semantic repository search |
| `/api/v1/repositories/{owner}/{repo}/index` | POST | Index repository |
| `/api/v1/repositories/{owner}/{repo}/index-status` | GET | Check indexing status |
| `/api/v1/chat` | POST | RAG chatbot |
| `/api/v1/chat/{conversation_id}/messages` | GET | Retrieve chat history |

Check the actual API documentation at:

`http://localhost:8000/docs`

## 🧠 9. How RAG Works in OpenScout

OpenScout uses Retrieval-Augmented Generation to help users ask questions about GitHub repositories.

### RAG Workflow

1. The user selects a repository.
2. The backend retrieves its documentation and relevant code content.
3. The content is divided into smaller chunks.
4. Sentence Transformers converts the chunks into vector embeddings.
5. The embeddings are stored in PostgreSQL using pgvector.
6. The user asks a question about the repository.
7. The question is converted into an embedding.
8. Semantic retrieval finds relevant repository chunks.
9. Retrieved context is provided to Mistral AI.
10. The LLM generates a context-based response with available source citations.

This enables developers to explore repositories without manually cloning and reading every file.

## 🚀 10. Deployment

### Frontend Deployment – Vercel

OpenScout's frontend is deployed on Vercel.

Live application:

https://openscout-ai-dun.vercel.app/

To configure another deployment:

1. Import the GitHub repository into Vercel.
2. Set the frontend root directory to `frontend`.
3. Select Vite as the framework.
4. Set the build command to `npm run build`.
5. Set the output directory to `dist`.
6. Configure `VITE_API_BASE_URL` with the public backend URL.
7. Deploy the application.

### Backend Deployment

The documented backend deployment options include Render, Railway, or a container-based hosting platform.

For Render, the typical configuration is:

- Root directory: `backend`
- Environment: Python
- Build command: `pip install -r requirements.txt`
- Start command: `uvicorn app.main:app --host 0.0.0.0 --port $PORT`

Configure the required environment variables and a persistent PostgreSQL database with pgvector.

Note: The frontend live demo is deployed on Vercel. Backend and database availability depend on their actual deployment configuration.

## 📈 11. Development Roadmap

- [x] Phase 1: Project Initialization and Architecture Setup
- [x] Phase 2: Frontend UI Development
- [x] Phase 3: FastAPI Backend Architecture
- [x] Phase 4: GitHub REST API Integration
- [x] Phase 5: Mistral AI Integration and Natural Language Query Understanding
- [x] Phase 6: Semantic Search, PostgreSQL, pgvector and RAG Chatbot
- [ ] Phase 7: Multi-Repository Comparison Engine and AI Explanations
- [ ] Phase 8: Advanced Production Hardening, CI/CD and Cloud Deployment

## 🔮 12. Future Enhancements

- Advanced repository recommendation algorithms.
- Improved repository comparison and AI explanations.
- More accurate semantic retrieval and reranking.
- Enhanced documentation indexing.
- Improved RAG answer verification and source grounding.
- Automated testing and CI/CD integration.
- Performance optimization and scalable cloud deployment.

## 🎯 13. Project Benefits

- Reduces the time required to discover relevant open-source projects.
- Simplifies GitHub repository discovery through natural-language queries.
- Helps beginners identify suitable projects.
- Provides semantic project recommendations.
- Enables conversational exploration of repository documentation.
- Supports informed repository selection through comparisons and explanations.

## 👨‍💻 14. Author and Repository

**Project:** OpenScout – AI-Powered Open Source Project Finder

**GitHub:** https://github.com/sujith2359/open-source-project-finder

**Live Demo:** https://openscout-ai-dun.vercel.app/

---

⭐ If you find OpenScout useful, consider starring the repository!

**Explore Open Source. Discover Projects. Build Better.**
