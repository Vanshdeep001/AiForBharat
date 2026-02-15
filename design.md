# Design Document

## Process Flow Diagram / Use-case Diagram

### User Interaction Flow

1. **User Interaction**
   - Open App
   - Select Language
   - Voice / Text Input

2. **AI CORE MODULE**
   - Processes user input through AI engine
   - Routes to appropriate service module

3. **Service Modules**
   - **Banking**: Account Help, Fraud Protection, ATM/Bank Locator
   - **Schemes**: Check Eligibility, Apply & Track
   - **Jobs**: Enter Skills, Find Jobs
   - **Marketplace**: Buy Products, Sell Products, Chat
   - **Rights**: Worker Rights, Farmer Rights, Business Rights, Senior Citizen Rights

4. **Action & Outcome**
   - Action Done
   - Follow-up Alerts

## Architecture Diagram

### Frontend Layer

- Voice Interface (Speech-to-Text/Text-to-Speech)
- WebApp (React Native)

### API Gateway & Load Balance

- Authentication Service
- Rate Limiting
- Fast API
- Request Routing

### Core Services (Microservices)

- **AI/NLP Engine**
  - Intent Recognition
  - Entity Extraction
  - Response Generation
- Banking Service
- Scheme Service
- Employment Service

### Data Layer

- User Database (MongoDB)
- Content Database (MongoDB)
- Cache Layer (Redis)
- Search Engine (Elasticsearch)

### External Integrations

- Government APIs
- Banking Partners

## Technologies to be used in the solution

### Frontend

- React.js
- Web Speech API – Speech-to-Text & Text-to-Speech
- Tailwind CSS

### Backend

- Python Flask – REST APIs & AI orchestration
- JWT Authentication – Secure user sessions
- Gunicorn + Nginx – Production deployment

### AI / Machine Learning

- Whisper – Speech-to-Text for user voice input
- BERT-based Intent Classification Model (PyTorch)
  - Trained to classify queries into: Banking, Government Scheme, Job, Marketplace
  - Retrieves relevant government scheme or job data
- Coqui TTS – Converts final response to voice output

### Web Scraping & Data Collection

- BeautifulSoup – Government scheme & policy scraping
- Selenium – Dynamic websites & JS-rendered content
- pdfplumber / PyPDF2 – Scheme & guideline PDFs

### Data & Storage

- MongoDB – Schemes, jobs, content
- FAISS Vector DB – Semantic search
- Redis – Caching frequent queries

### Cloud & Deployment

- AWS EC2 & S3 – Model hosting & dataset storage
- Docker – Reproducible environment

## Key Design Principles

1. **Voice-First Design**: All features accessible through voice commands
2. **Location Intelligence**: Automatic detection and filtering of state-specific schemes
3. **Multilingual Support**: Support for local languages and dialects
4. **Unified Platform**: Single interface for all services
5. **Accessibility**: Designed for low-literacy users
6. **Security**: JWT authentication and fraud detection
7. **Scalability**: Microservices architecture with load balancing
