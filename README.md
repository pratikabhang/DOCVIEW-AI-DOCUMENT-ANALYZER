# 📄 DocView — AI Document Analyzer

> Transform documents into actionable insights with AI-powered summarization, contextual conversations, intelligent text analysis, and document processing.

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-20%20LTS-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-4.x-000000?logo=express&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?logo=firebase&logoColor=black)
![AI Powered](https://img.shields.io/badge/AI-Powered-8A2BE2)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

## 📑 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation and Setup](#-installation-and-setup)
- [Environment Configuration](#-environment-configuration)
- [Usage and Examples](#-usage-and-examples)
- [API Documentation](#-api-documentation)
- [Mobile Application](#-mobile-application)
- [Docker Deployment](#-docker-deployment)
- [Production Deployment](#-production-deployment)
- [Security](#-security)
- [Testing](#-testing)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

## 📖 Overview

**DocView — AI Document Analyzer** is a full-stack application designed to help users understand, analyze, and interact with documents using artificial intelligence.

The application combines a web frontend, backend APIs, AI/ML components, and a mobile application. Users can upload supported documents, generate summaries, extract key insights, analyze sentiment, rewrite content, and ask questions about document content.

The repository also includes API documentation, containerization configuration, Kubernetes resources, NGINX configuration, and CI/CD automation files.

### Project Goals

- Reduce the time required to understand lengthy documents.
- Convert unstructured document content into concise, useful insights.
- Enable contextual question answering using document content.
- Provide AI-assisted text analysis and rewriting.
- Support modular development across web, backend, AI/ML, and mobile components.
- Provide deployment and API documentation for developers.

## ✨ Features

### AI-Powered Document Analysis

- **Document Summarization:** Generate concise summaries of supported documents.
- **Key Insight Extraction:** Identify important information and discussion points.
- **Contextual AI Chat:** Ask questions about document content.
- **Sentiment Analysis:** Analyze text for sentiment and emotional indicators.
- **Content Rewriting:** Rewrite or rephrase text according to a requested style.
- **Actionable Recommendations:** Generate recommendations based on document content.
- **Bullet-Point Summaries:** Present information in an easy-to-scan format.
- **Document Categorization:** Organize documents based on their content.
- **Multilingual Processing:** Support language-related document processing where configured.
- **Voice Interaction:** Support voice-related workflows through available integrations.

### Application Features

- **Authentication:** Registration, login, and password-reset workflows.
- **Document History:** Access previously processed documents where supported.
- **Profile Management:** Manage supported profile settings.
- **Responsive Web Interface:** Access the application through a browser.
- **Mobile Application:** Separate React Native and Expo-based mobile project.
- **API Documentation:** OpenAPI specification and Swagger-related tooling.
- **Deployment Infrastructure:** Docker Compose, Kubernetes, and NGINX configuration.
- **CI/CD Integration:** GitHub Actions and Jenkins configuration files.

Feature availability depends on the implementation, service credentials, and deployment configuration.

## 🛠️ Tech Stack

### Frontend

| Technology | Purpose |
|---|---|
| React 18 | User interface |
| Material UI | UI components |
| Axios | HTTP requests |
| React Router | Client-side navigation |
| Tailwind CSS | Utility-based styling |
| CRACO | Create React App configuration overrides |
| Jest | JavaScript testing |
| React Testing Library | Component testing |

### Backend

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js 4 | HTTP server and API routing |
| Firebase Admin SDK | Server-side Firebase integration |
| Firebase Authentication | Authentication integration |
| Google Generative AI | AI model integration |
| Google APIs | External Google service integration |
| Axios | HTTP communication |
| Multer / Formidable / Busboy | Multipart and file-upload handling |
| Mammoth | Word document processing |
| pdf-parse | PDF text extraction |
| Swagger / OpenAPI | API documentation |
| Redis client | Cache integration |
| dotenv | Environment configuration |

### AI and Machine Learning

- Natural Language Processing (NLP)
- Retrieval-Augmented Generation (RAG)
- LangChain-related document processing
- Named Entity Recognition (NER)
- Part-of-Speech (POS) tagging
- Sentiment analysis
- Document summarization and contextual question answering

The specific model providers, pipelines, and algorithms depend on the implementations under `ai_ml/` and `backend/`.

### Data and Infrastructure

| Technology | Purpose |
|---|---|
| Firebase / Firestore | Authentication and configured data services |
| MongoDB | Document and application data storage where configured |
| Redis | Caching where configured |
| RabbitMQ | Asynchronous messaging where configured |
| Docker | Containerization |
| Kubernetes | Container orchestration |
| NGINX | Reverse proxy and traffic management |
| GitHub Actions | CI automation |
| Jenkins | CI/CD automation |
| Vercel / Render / Netlify | Hosting integrations documented by the project |
| React Native / Expo | Mobile application |

Not every listed service is required for every local development workflow.

## 🏗️ Architecture

DocView separates the user interface, backend APIs, AI/ML processing, and mobile application into distinct components.

```text
                         Users
                           |
              +------------+------------+
              |                         |
              v                         v
        Web Application           Mobile Application
           (React)                (React Native/Expo)
              |                         |
              +------------+------------+
                           |
                           v
                      Backend API
                       (Express)
                           |
             +-------------+-------------+
             |             |             |
             v             v             v
       Authentication   Document      API Routes
        and Sessions    Processing
                           |
                           v
                    AI/ML Processing
                           |
               +-----------+-----------+
               |           |           |
               v           v           v
           Summaries    AI Chat    Text Analysis
               |           |           |
               +-----------+-----------+
                           |
                           v
                Configured Data Services
             Firebase / MongoDB / Redis
```

This is a logical architecture overview. The actual request flow, service boundaries, and storage configuration depend on the implementation.

### Document Processing Workflow

1. The user selects and uploads a supported document.
2. The backend receives the uploaded file.
3. The application extracts document text using the configured processing libraries.
4. The AI/ML layer processes the extracted content.
5. The requested operation generates a summary, analysis, or contextual response.
6. The application returns the result to the client.
7. Document history and related data are persisted where configured.

## 📂 Project Structure

```text
DOCVIEW-AI-DOCUMENT-ANALYZER/
├── .devcontainer/           # Development container configuration
├── .github/
│   └── workflows/           # GitHub Actions workflows
├── ai_ml/                   # AI and machine learning components
├── backend/                 # Backend application
├── frontend/                # Web frontend
├── mobile-app/              # React Native / Expo application
├── kubernetes/              # Kubernetes resources
├── nginx/                   # NGINX configuration
├── .env.example             # Environment variable template
├── docker-compose.yml       # Container orchestration configuration
├── Jenkinsfile              # Jenkins pipeline
├── eslint.config.mjs        # ESLint configuration
├── jenkins_cicd.sh          # Jenkins CI/CD helper script
├── manage_docuthinker.sh    # Project management helper script
├── ai_ml_models.ipynb       # AI/ML experimentation notebook
├── next.config.mjs          # Next.js configuration
├── openapi.yaml             # OpenAPI specification
├── package.json             # Root dependencies and scripts
├── package-lock.json        # npm dependency lockfile
├── tailwind.config.js       # Tailwind CSS configuration
├── postcss.config.mjs       # PostCSS configuration
└── README.md                # Project documentation
```

Some directories may contain their own configuration files and dependencies. Review the relevant directory before installing or running a component independently.

## 💻 Prerequisites

For the main application, prepare the following:

- **Node.js:** Use Node.js 20 or an otherwise verified compatible version. The existing project documentation warns about compatibility issues with newer versions and Firebase Admin.
- **npm:** Installed with Node.js.
- **Git:** For cloning and version control.
- **Firebase project and credentials:** Required for the Firebase integrations you enable.
- **Google AI API key:** Required for AI features that use the configured Google AI service.
- **Redis:** Required if the selected backend workflow uses Redis.
- **MongoDB:** Required if the selected backend workflow uses MongoDB.
- **Docker and Docker Compose:** Optional for containerized development.
- **Python:** Required only if the selected AI/ML components use Python.

Additional services such as RabbitMQ, Kubernetes, and Jenkins are optional unless required by the specific workflow you intend to run.

Verify your installation:

```bash
node --version
npm --version
git --version
```

## 🚀 Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/pratikabhang/DOCVIEW-AI-DOCUMENT-ANALYZER.git
cd DOCVIEW-AI-DOCUMENT-ANALYZER
```

### 2. Install Root Dependencies

The root `package.json` defines scripts for starting the frontend, building it, running tests, and starting the backend.

```bash
npm install
```

The root installation does not necessarily install dependencies for every independently configured component. If `frontend/`, `backend/`, `ai_ml/`, or `mobile-app/` contains its own dependency manifest, follow that component's instructions as well.

### 3. Configure Environment Variables

Create a local environment file from the provided template.

**macOS / Linux**

```bash
cp .env.example .env
```

**Windows PowerShell**

```powershell
Copy-Item .env.example .env
```

Populate the variables required by the services you intend to use.

The repository's environment template includes these configuration categories:

| Variable | Purpose |
|---|---|
| `FIREBASE_API_KEY` | Firebase client configuration |
| `FIREBASE_AUTH_DOMAIN` | Firebase authentication domain |
| `FIREBASE_PROJECT_ID` | Firebase project identifier |
| `FIREBASE_STORAGE_BUCKET` | Firebase storage configuration |
| `FIREBASE_MESSAGING_SENDER_ID` | Firebase messaging configuration |
| `FIREBASE_APP_ID` | Firebase application identifier |
| `FIREBASE_MEASUREMENT_ID` | Firebase analytics configuration |
| `FIREBASE_PRIVATE_KEY` | Firebase Admin service-account key |
| `FIREBASE_CLIENT_EMAIL` | Firebase Admin service-account email |
| `JWT_SECRET` | JWT signing secret |
| `REDIS_URL` | Redis connection URL |
| `GOOGLE_AI_API_KEY` | Google AI service credential |
| `PORT` | Application port where supported |

The template also lists additional Firebase Admin service-account fields.

**Important:** These variables must be populated with the correct values. Do not commit your `.env` file or publish private service-account credentials. Use the minimum required credentials for local development.

### 4. Start the Frontend

```bash
npm start
```

The root `start` script runs the frontend's start command. Open the URL printed in the terminal.

If running the frontend independently:

```bash
cd frontend
npm install
npm start
```

If npm reports peer-dependency conflicts, investigate the incompatible packages first. Use `npm install --legacy-peer-deps` only when necessary and after reviewing the implications.

### 5. Start the Backend

Open a separate terminal from the repository root:

```bash
npm run server
```

The root script invokes Nodemon for `backend/index.js`.

Alternatively, run the backend independently if its own package configuration supports that workflow:

```bash
cd backend
npm install
```

Use the backend's configured start script and environment settings. Do not assume the backend port is the same as the frontend port.

### 6. Connect the Frontend to the Backend

The Docker Compose configuration uses `REACT_APP_BACKEND_URL` for frontend-to-backend communication.

For local development, configure the frontend using the environment variable expected by its source code. For example:

```env
REACT_APP_BACKEND_URL=http://localhost:3000
```

This is an example based on the Compose configuration, not a guarantee that every frontend component reads the same variable.

Ensure the backend is running, the API URL is correct, and CORS permits the frontend origin.

## ⚙️ Environment Configuration

DocView integrates with external services, so the required configuration depends on the selected features.

Recommended practices:

- Use `.env.example` as the starting point.
- Keep real credentials in an ignored local `.env` file or a managed secrets service.
- Configure frontend variables separately from backend secrets.
- Never expose `JWT_SECRET` or Firebase Admin private keys to browser code.
- Configure Redis and database URLs only when the corresponding integrations are enabled.
- Use separate development and production credentials.
- Validate required variables at application startup.

The provided `.env.example` is a variable template; check the source code for required values, defaults, and component-specific configuration.

## ▶️ Usage and Examples

### Web Application

1. Start the backend and frontend.
2. Open the frontend URL in a browser.
3. Sign in or create an account if authentication is enabled.
4. Upload a supported document.
5. Select an available analysis operation.
6. Review the generated output.
7. Ask contextual questions or explore other supported document features.

The exact interface and available operations depend on the current frontend implementation.

### Example AI Document Workflow

A typical workflow might look like this:

```text
Document
   |
   v
Text Extraction
   |
   v
AI Processing
   |
   +----> Summary
   |
   +----> Key Insights
   |
   +----> Sentiment Analysis
   |
   +----> Contextual Questions
   |
   v
Results in the Application
```

### API Requests

The repository includes an OpenAPI specification in `openapi.yaml`.

Inspect that file to identify the exact API paths, HTTP methods, authentication requirements, and request schemas before sending requests.

Example request structure:

```bash
curl -X GET "http://localhost:3000/" \
  -H "Accept: application/json"
```

This is a generic example. Replace the path with a documented endpoint that is actually registered by the backend.

## 📚 API Documentation

DocView includes `openapi.yaml` and dependencies for Swagger-based API documentation.

To explore the API:

1. Open `openapi.yaml`.
2. Review the documented paths and HTTP methods.
3. Check authentication requirements and request schemas.
4. Start the backend using its configured development command.
5. Use Postman, Insomnia, or cURL to test the documented endpoints.

Swagger UI is available only if the backend explicitly registers and serves it. Consult the backend source code for the documentation URL.

## 📱 Mobile Application

The repository contains a separate `mobile-app/` directory for the React Native and Expo application.

To explore the mobile project:

```bash
cd mobile-app
npm install
npx expo start
```

Follow the Expo terminal instructions to run the application in an emulator or on a compatible device.

Mobile-specific environment variables, Firebase configuration, and supported workflows should be configured according to the files inside `mobile-app/`.

## 🐳 Docker Deployment

The repository includes a root `docker-compose.yml` with service definitions for the backend, frontend, and Firebase-related configuration.

Before starting containers, review the Compose file and verify that its referenced Dockerfiles, environment files, ports, images, and service dependencies exist and are configured correctly.

If the configuration is valid for your environment, start the services with:

```bash
docker compose up --build
```

To run the containers in the background:

```bash
docker compose up --build -d
```

To inspect container logs:

```bash
docker compose logs -f
```

To stop the services:

```bash
docker compose down
```

**Note:** The checked-in Compose configuration should be validated before use. In particular, verify the Firebase service image, backend dependencies, and frontend/backend port configuration. The command alone does not guarantee that every service will start successfully.

## ☁️ Production Deployment

The repository contains configuration for multiple deployment approaches.

### Frontend

The project documentation identifies Vercel and Netlify as frontend hosting options.

Typical deployment steps:

1. Import the repository into your chosen hosting platform.
2. Configure the frontend build settings.
3. Set the required public frontend configuration variables.
4. Configure the backend API URL.
5. Deploy and test navigation, authentication, and API requests.

### Backend

The backend can be deployed to a Node.js-compatible hosting environment.

1. Configure the production start command.
2. Provide required environment variables and secrets.
3. Configure database and external-service connections.
4. Set the listening port according to the hosting platform.
5. Configure HTTPS, CORS, logging, and health checks.
6. Test authentication and document-processing workflows after deployment.

### Containers and Orchestration

The repository also includes Kubernetes and NGINX configuration. Review the manifests, container build files, service definitions, and deployment secrets before using these resources in production.

The presence of deployment configuration does not by itself guarantee that every deployment target is currently active or healthy.

## 🔐 Security

Document-analysis applications can process sensitive personal, academic, business, and financial information. Treat uploaded files and generated results accordingly.

- **Secrets:** Never commit private keys, service-account credentials, JWT secrets, or production `.env` files.
- **File uploads:** Validate file types, size limits, and content before processing.
- **Authentication:** Enforce authentication and authorization on protected backend endpoints.
- **Data privacy:** Define document retention and deletion behavior and avoid logging sensitive document contents.
- **AI output:** Treat generated summaries and recommendations as potentially inaccurate; verify important information against the source document.
- **API keys:** Restrict external-service credentials and rotate any exposed secrets.
- **CORS:** Allow only appropriate frontend origins in production.
- **Dependencies:** Audit dependencies and address known vulnerabilities.
- **Infrastructure:** Restrict database access, secure Redis, and avoid exposing internal service ports.
- **Transport security:** Use HTTPS in public deployments.
- **Document access:** Ensure one user's uploaded documents cannot be accessed by another user without authorization.

## 🧪 Testing and Code Quality

The root `package.json` includes commands for testing and formatting.

Run the configured tests:

```bash
npm test
```

Run the configured formatting script:

```bash
npm run format
```

The root test script delegates to the frontend test command. Backend and AI/ML tests may require separate commands within their respective components.

A successful command should not be assumed until it has been run in the configured environment. Add tests for document parsing, authentication, AI response handling, API validation, and authorization as appropriate.

## 🔮 Future Improvements

Potential improvements include:

- Expand automated backend and AI/ML integration tests.
- Add document-processing benchmarks and performance monitoring.
- Improve upload validation and file-size controls.
- Document every API endpoint and example payload.
- Provide component-specific environment templates.
- Add structured logging and tracing.
- Improve accessibility and mobile responsiveness.
- Implement clear document retention and deletion policies.
- Validate Docker Compose and Kubernetes deployments in CI.
- Add dependency scanning and secret scanning to CI/CD workflows.

These are proposed improvements, not claims about functionality already implemented.

## 🤝 Contributing

Contributions, bug reports, and improvements are welcome.

1. Fork the repository.
2. Clone your fork:

   ```bash
   git clone https://github.com/<your-username>/DOCVIEW-AI-DOCUMENT-ANALYZER.git
   cd DOCVIEW-AI-DOCUMENT-ANALYZER
   ```

3. Create a feature branch:

   ```bash
   git checkout -b feature/your-feature-name
   ```

4. Make changes in the relevant component.
5. Run the available tests and formatting checks.
6. Commit your changes:

   ```bash
   git add .
   git commit -m "Improve document analysis functionality"
   ```

7. Push your branch:

   ```bash
   git push origin feature/your-feature-name
   ```

8. Open a pull request describing the change, testing performed, and any configuration updates.

Never include credentials, private keys, real user documents, or sensitive environment files in a contribution.

## 📄 License

The root `package.json` declares the **MIT License**. Review the repository's `LICENSE` file for the applicable copyright notice and terms.

Third-party libraries and models may have their own licensing conditions. Preserve required notices and comply with their terms.

## 👨‍💻 Author

**Pratik Abhang**

- GitHub: [@pratikabhang](https://github.com/pratikabhang)
- Repository: [DOCVIEW-AI-DOCUMENT-ANALYZER](https://github.com/pratikabhang/DOCVIEW-AI-DOCUMENT-ANALYZER)

---

⭐ If you find this project useful, consider starring the repository.

*Understand documents faster. Discover insights. Work smarter with AI.*
