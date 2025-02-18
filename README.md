<p align="center">
  <h1 align="center">📱 Azure OpenAI Medical Phone Appointments</h1>
  <p align="center">An intelligent phone-based appointment scheduling system powered by Azure OpenAI GPT-4 and Twilio, featuring real-time voice interactions and natural language processing.</p>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#architecture">Architecture</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#configuration">Configuration</a> •
  <a href="#development-setup">Development</a> •
  <a href="#contributing">Contributing</a>
</p>

<p align="center">
  <a href="https://azure.microsoft.com/"><img src="https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure"></a>
  <a href="https://openai.com/"><img src="https://img.shields.io/badge/OpenAI-412991.svg?style=for-the-badge&logo=OpenAI&logoColor=white" alt="OpenAI"></a>
  <a href="https://www.twilio.com/"><img src="https://img.shields.io/badge/Twilio-F22F46?style=for-the-badge&logo=twilio&logoColor=white" alt="Twilio"></a>
  <a href="https://fastapi.tiangolo.com/"><img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI"></a>
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python"></a>
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge" alt="License: MIT"></a>
</p>

### 🌟 Features

- 🎯 Real-time voice interactions using GPT-4
- 📞 Phone-based appointment scheduling
- 🤖 Natural language understanding
- ✨ Automated voice responses
- 📝 Appointment information collection
- 📱 SMS confirmations
- 🔄 Real-time availability checks
- 🌐 Multi-language support

### 🏗️ Architecture

```mermaid
graph LR
    A[Patient Call] -->|Twilio Voice| B[FastAPI Server]
    B -->|WebSocket| C[Azure OpenAI GPT-4]
    C -->|Stream| B
    B -->|Audio| A
    B -->|Store| D[(Azure SQL DB)]
    B -->|SMS| E[Twilio SMS]
```

### 🔄 Data Flow
## Incoming Call
```mermaid
sequenceDiagram
    Patient->>+Twilio: Calls medical center
    Twilio->>+FastAPI: Initiates WebSocket
    FastAPI->>+Azure OpenAI: Streams audio
    Azure OpenAI->>-FastAPI: Processes speech
    FastAPI->>-Twilio: Returns response
    Twilio->>-Patient: Plays response
```

### 🛠️ Tech Stack
```html
Backend Framework: FastAPI
AI Model: Azure OpenAI GPT-4
Voice Services: Twilio
Database: Azure SQL
Runtime: Python 3.8+
WebSocket: asyncio/websockets
Deployment: Azure App Service
```
### 🚀 Quick Start
## 1. Clone the repository
```bash
git clone https://github.com/yourusername/azure-openai-phone-appointments.git
cd azure-openai-phone-appointments

## Set up environment variables
cp .env.example .env

## Configure the following in .env:
OPENAI_API_KEY=your_azure_openai_key
OPENAI_API_ENDPOINT=your_azure_endpoint
PORT=5050

## 3. Install dependencies
pip install -r requirements.txt

## 4. Run the application
python app.py
```
### 🔧 Configuration
## The system uses several key configurations:
```python
SYSTEM_MESSAGE = """
You are an AI assistant acting as a medical center receptionist.
Tasks:
1. Greet callers
2. Collect appointment information:
   - Doctor's name
   - Caller's name
   - Phone number
   - Appointment date/time
"""
```
### 📊 API Endpoints
## 🔐 Security Features

- 🔒 Secure WebSocket connections
- 🔑 API key authentication  
- 🛡️ Input validation
- 🔐 HIPAA-compliant communications

## 📡 WebSocket Communication

## The application handles bi-directional audio streaming:

- 📤 Incoming audio from Twilio
- 📥 Processed responses from Azure OpenAI
- 🔄 Real-time speech detection
- ⚡ Low-latency voice interactions

### 🎯 Key Components
## 1. Call Handler
```python
@app.api_route("/incoming-call", methods=["GET", "POST"])
async def handle_incoming_call(request: Request):
    # Handles incoming Twilio calls

## 2. Media Stream
```python
@app.websocket("/media-stream")
async def handle_media_stream(websocket: WebSocket):
    # Manages real-time audio streaming
```
### 📝 Contributing
1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Push to the branch
5. Open a Pull Request

### 👥 Support
For support, please open an issue in the repository or contact

### 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
 
### 🌐 Explore AI Resources

- **AiMegos**: [Discover Vamsi Kethu's AI Leadership](https://aimegos.com/team-vamsi-kethu/)  
- **AgentsInfinite**: [Where Vision Meets Velocity](https://agentsinfinite.com/)

### 💬 Support
- 📧 Email: contactus@agentsinfinite.com  
- 💭 Discord: [Join our server](#)  
- 🐦 Twitter: [@agentsinfinite](https://twitter.com/agentsinfinite)

---

Made with ❤️ by VamK2 @ Aimegos | AgentsInfinite  
🌐 [Website](https://aimegos.com/) • 📚 [Documentation](#) • ✍️ [Blog](#)













