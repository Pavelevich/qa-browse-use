# Matrix QA Test Runner

<div align="center">

![Matrix QA Test Runner](https://img.shields.io/badge/Matrix-QA%20Test%20Runner-00ff00?style=for-the-badge&logo=matrix&logoColor=00ff00)

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com)
[![Python](https://img.shields.io/badge/python-3.8+-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com)
[![WebSocket](https://img.shields.io/badge/WebSocket-Real--time-ff6600?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)

**AI-Powered Browser Automation & QA Testing Platform**

*Harness the power of multiple AI providers to automate web testing with real-time monitoring and comprehensive reporting.*

[Features](#features) • [Installation](#installation) • [Configuration](#configuration) • [Usage](#usage) • [API](#api-documentation) • [Contributing](#contributing)

</div>

---

## 🚀 Overview

Matrix QA Test Runner is a cutting-edge, AI-powered testing platform designed to revolutionize quality assurance workflows. Built with a Matrix-themed interface, it combines the power of multiple AI providers with browser automation to deliver comprehensive, intelligent testing solutions.

### 🎯 Key Highlights

- **Multi-AI Integration**: Support for Claude, GPT, DeepSeek, and more
- **Real-time Monitoring**: Live browser screenshots and execution tracking
- **JIRA Integration**: Seamless ticket management and automation
- **Video Recording**: Capture test executions for analysis
- **Enterprise Ready**: JWT authentication, role-based access, and MongoDB persistence

---

## ✨ Features

### 🤖 **AI-Powered Testing**
- **Multiple AI Providers**: Anthropic Claude, OpenAI GPT, DeepSeek, Mistral AI, Google Gemini
- **Intelligent Test Generation**: Natural language instructions converted to automated actions
- **Smart Error Handling**: AI-driven debugging and recovery mechanisms

### 🖥️ **Real-time Monitoring**
- **Live Screenshots**: WebSocket-powered real-time browser viewing
- **Video Recording**: MP4/GIF capture of test executions with FFmpeg support
- **Progress Tracking**: Step-by-step execution monitoring with detailed logs

### 🔐 **Enterprise Security**
- **JWT Authentication**: Secure token-based authentication system
- **Role-based Access**: Admin and user permission levels
- **API Key Management**: Encrypted storage of AI provider credentials

### 📊 **Comprehensive Reporting**
- **Execution History**: Detailed test run archives with searchable metadata
- **Video Attachments**: Link recordings to specific test executions
- **Export Capabilities**: Download results and videos for offline analysis

### 🎫 **JIRA Integration**
- **Ticket Automation**: Execute tests directly from JIRA tickets
- **Label-based Filtering**: Automatic detection of automation-ready tickets
- **Seamless Workflow**: Bridge between issue tracking and test execution

### ⚙️ **Advanced Configuration**
- **Video Settings**: Configurable resolution, quality, and frame rates
- **API Configuration**: Per-model API key management
- **User Management**: Admin panel for user creation and management

---

## 🛠️ Installation

### Prerequisites

- **Python 3.8+**
- **MongoDB 4.0+**
- **Node.js 14+** (for frontend dependencies)
- **FFmpeg** (optional, for MP4 video recording)

### Quick Start

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/qa-remote-browser.git
   cd qa-remote-browser
   ```

2. **Set Up Python Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Install Browser Dependencies**
   ```bash
   # Install browser-use package (modified version included)
   cd browser_use_mod/browser-use
   pip install -e .
   cd ../..
   
   # Install Playwright browsers
   playwright install
   ```

4. **Install Node.js Dependencies** (if needed)
   ```bash
   npm install
   ```

5. **Configure Environment Variables**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

6. **Start the Application**
   ```bash
   python main.py
   ```

7. **Access the Application**
   - Open your browser to `http://localhost:8000`
   - Default credentials: `admin` / `admin`

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the root directory:

```bash
# Database Configuration
MONGO_URI=mongodb://localhost:27017/matrix_qa
JWT_SECRET=your_jwt_secret_key_here
ENCRYPTION_KEY=your_32_character_encryption_key

# API Keys (Optional - can be set in UI)
ANTHROPIC_API_KEY=sk-ant-your-key-here
OPENAI_API_KEY=sk-your-openai-key-here
DEEPSEEK_API_KEY=your-deepseek-key-here

# JIRA Integration (Optional)
JIRA_URL=https://your-company.atlassian.net
JIRA_USERNAME=your-email@company.com
JIRA_API_TOKEN=your-jira-api-token
JIRA_AUTOMATION_LABELS=qa-automation,matrix-test,automated-test

# Server Configuration
PORT=8000
API_KEY=qa_secret_key
```

### MongoDB Setup

1. **Install MongoDB**
   ```bash
   # Ubuntu/Debian
   sudo apt-get install mongodb
   
   # macOS
   brew install mongodb-community
   
   # Or use Docker
   docker run -d -p 27017:27017 --name mongodb mongo:latest
   ```

2. **Verify Connection**
   ```bash
   mongosh mongodb://localhost:27017/matrix_qa
   ```

### JIRA Integration Setup

1. **Generate API Token**
   - Go to [Atlassian Account Settings](https://id.atlassian.com/manage-profile/security/api-tokens)
   - Create new API token
   - Add to environment variables

2. **Configure Automation Labels**
   - Set `JIRA_AUTOMATION_LABELS` with comma-separated labels
   - Tickets with these labels will appear in the automation interface

---

## 🎮 Usage

### Getting Started

1. **Login**
   - Access the Matrix-themed login interface
   - Use default credentials: `admin` / `admin`
   - Create additional users via the admin panel

2. **Configure API Settings**
   - Click the "CONFIG" button in the control panel
   - Add your AI provider API keys
   - Test connections to ensure proper setup

3. **Run Your First Test**
   ```
   Navigate to https://example.com and verify the page title contains "Example"
   ```

### AI Provider Configuration

#### Anthropic Claude
```bash
# API Key format: sk-ant-...
ANTHROPIC_API_KEY=sk-ant-api03-your-key-here
```

#### OpenAI
```bash
# API Key format: sk-...
OPENAI_API_KEY=sk-your-openai-key-here
```

#### DeepSeek
```bash
# API Key from DeepSeek platform
DEEPSEEK_API_KEY=your-deepseek-key-here
```

### Video Recording

1. **Enable Recording**
   - Go to CONFIG → VIDEO SETTINGS
   - Enable "VIDEO RECORDING"
   - Configure resolution and quality

2. **View Recordings**
   - Access EXECUTION HISTORY
   - Download videos from completed test runs
   - Supports both MP4 (with FFmpeg) and GIF formats

### JIRA Integration

1. **View Automation Tickets**
   - Click "JIRA TICKETS" button
   - Browse tickets marked with automation labels
   - Filter by status and search terms

2. **Execute from JIRA**
   - Select a ticket from the list
   - Click "🚀 Execute Test"
   - Instructions are automatically loaded and executed

---

## 📡 API Documentation

### Authentication

All API endpoints require authentication via JWT token or API key.

#### Login
```http
POST /api/auth/authenticate
Content-Type: application/json

{
  "username": "admin",
  "password": "admin"
}
```

#### Headers for Authenticated Requests
```http
Authorization: Bearer <jwt_token>
# OR
X-API-Key: qa_secret_key
```

### Core Endpoints

#### Create Test Session
```http
POST /sessions
X-API-Key: qa_secret_key

Response:
{
  "session_id": "uuid-string",
  "status": "created"
}
```

#### Execute Test
```http
POST /sessions/{session_id}/tasks
Authorization: Bearer <token>
Content-Type: application/json

{
  "instructions": "Navigate to google.com and search for 'AI testing'",
  "browser_visible": true,
  "api_provider": "anthropic",
  "api_model": "claude-3-5-sonnet-20240620",
  "use_default_key": true
}
```

#### Get Execution History
```http
GET /api/history
Authorization: Bearer <token>

Response:
{
  "success": true,
  "history": [
    {
      "_id": "...",
      "title": "Test execution",
      "content": "Results...",
      "timestamp": "2024-01-01T12:00:00Z",
      "model": "anthropic/claude-3-5-sonnet"
    }
  ]
}
```

### WebSocket Endpoints

#### Real-time Updates
```javascript
const socket = new WebSocket('ws://localhost:8000/ws/{session_id}');

// Message types:
// - session_status
// - task_update
// - task_complete
// - task_error
// - recording_status
```

#### Live Screenshots
```javascript
const screenshotSocket = new WebSocket('ws://localhost:8000/ws/screenshot/{session_id}');

// Receives base64-encoded screenshots in real-time
```

---

## 🏗️ Architecture

### Backend Components

- **FastAPI**: RESTful API and WebSocket server
- **MongoDB**: Document storage for users, history, and videos
- **Motor**: Async MongoDB driver
- **JWT**: Token-based authentication
- **Cryptography**: API key encryption
- **Browser-use**: AI-powered browser automation
- **FFmpeg**: Video processing (optional)

### Frontend Components

- **Vanilla JavaScript**: No framework dependencies
- **WebSocket**: Real-time communication
- **Bootstrap**: UI components and grid system
- **Matrix Theme**: Custom CSS with retro-futuristic styling

### File Structure

```
qa-remote-browser/
├── main.py                    # Application entry point
├── config.py                  # Configuration management
├── mongodb_config.py          # Database configuration
├── auth.py                    # Authentication logic
├── .env                       # Environment variables
├── requirements.txt           # Python dependencies
├── matrix_users.json          # User data storage
├── package.json               # Node.js dependencies
├── package-lock.json          # Node.js lock file
├── backend/                   # Backend application code
│   ├── models/               # Data models
│   │   ├── __init__.py
│   │   └── schemas.py        # Pydantic schemas
│   ├── mongo_routes/         # MongoDB-specific routes
│   │   ├── __init__.py
│   │   ├── auth_routes.py    # MongoDB authentication routes
│   │   └── history_routes.py # Execution history routes
│   ├── routes/               # API route handlers
│   │   ├── __init__.py
│   │   ├── jira_routes.py    # JIRA integration endpoints
│   │   ├── session_routes.py # Session management
│   │   ├── task_routes.py    # Task execution endpoints
│   │   ├── video_routes.py   # Video recording endpoints
│   │   └── websocket_routes.py # WebSocket handlers
│   ├── services/             # Business logic services
│   │   ├── __init__.py
│   │   ├── ai_providers.py   # AI provider integrations
│   │   ├── jira_service.py   # JIRA service logic
│   │   ├── screenshot.py     # Screenshot capture service
│   │   ├── test_runner.py    # Test execution engine
│   │   └── video_recorder.py # Video recording service
│   └── utils/               # Utility functions
│       ├── __init__.py
│       └── helpers.py       # Helper functions
├── browser_use_mod/          # Modified browser-use package
│   └── browser-use/         # Browser automation library
├── frontend/                 # Static web files
│   ├── index.html           # Main application interface
│   ├── css/
│   │   └── matrix-style.css # Matrix-themed styling
│   └── js/
│       ├── jira-manager.js  # JIRA integration frontend
│       └── matrix-app.js    # Main application logic
├── venv/                    # Python virtual environment
└── cloudflared.deb          # Cloudflare tunnel binary
```

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Development Setup

1. **Fork the Repository**
   ```bash
   git clone https://github.com/yourusername/qa-remote-browser.git
   cd qa-remote-browser
   ```

2. **Create Feature Branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Set Up Development Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   
   # Install modified browser-use package
   cd browser_use_mod/browser-use
   pip install -e .
   cd ../..
   
   # Install Node.js dependencies
   npm install
   
   # Install development dependencies (if available)
   pip install -r requirements-dev.txt  # Development dependencies
   ```

4. **Run Tests**
   ```bash
   pytest backend/tests/  # Run backend tests
   ```

### Contribution Guidelines

- **Code Style**: Follow PEP 8 for Python, ESLint for JavaScript
- **Testing**: Add tests for new features
- **Documentation**: Update README and docstrings
- **Commits**: Use conventional commit messages

### Areas for Contribution

- 🔧 **New AI Providers**: Add support for additional AI services
- 🎨 **UI Improvements**: Enhance the Matrix-themed interface
- 📊 **Reporting Features**: Advanced analytics and dashboards
- 🧪 **Testing Framework**: Unit and integration test coverage
- 📖 **Documentation**: Tutorials and advanced usage guides

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Matrix QA Test Runner

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 Acknowledgments

- **[Browser-use](https://github.com/browser-use/browser-use)**: Foundation for AI-powered browser automation
- **[WarmShao](https://github.com/WarmShao)**: Contributor to the browser-use project
- **FastAPI Community**: For the excellent web framework
- **Matrix Franchise**: Inspiration for the iconic green-on-black aesthetic

---

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/qa-remote-browser/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/qa-remote-browser/discussions)
- **Documentation**: [Wiki](https://github.com/yourusername/qa-remote-browser/wiki)

---

<div align="center">

**Made with ❤️ for the QA Community**

*Follow the white rabbit... into automated testing excellence.*

[![Stars](https://img.shields.io/github/stars/yourusername/qa-remote-browser?style=social)](https://github.com/yourusername/qa-remote-browser/stargazers)
[![Forks](https://img.shields.io/github/forks/yourusername/qa-remote-browser?style=social)](https://github.com/yourusername/qa-remote-browser/network/members)

</div>
