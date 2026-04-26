# Voice Agent

A real-time voice AI assistant powered by Google Gemini and VideoSDK. This application provides intelligent, conversational voice interactions with natural language understanding and real-time audio processing.

## ⚠️ Sample Code Notice

**This is sample code for demonstration purposes.** For production use, additional features such as error handling, logging, security validation, and performance optimization should be implemented.

## Features

- 🎙️ **Real-time Voice Interaction** - Process and respond to voice input in real-time
- 🤖 **AI-Powered Responses** - Leverages Google Gemini 3.1 Flash for intelligent responses
- 📞 **Call Management** - Handles incoming calls with automatic agent response
- 🎵 **Natural Voice** - Uses high-quality voice synthesis (Aoede voice)
- 🔌 **Easy Integration** - Simple setup with environment variables

## Prerequisites

- Python 3.8+
- pip (Python package manager)
- API Keys:
  - Google Gemini API key
  - VideoSDK API credentials (optional for Groq alternative)

## Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd Voice-Agent-main
   ```

2. **Create a virtual environment**

   ```bash
   python -m venv venv

   # On Windows
   .\venv\Scripts\activate

   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   Create a `.env` file in the project root:
   ```
   GOOGLE_API_KEY=your_google_gemini_api_key_here
   GROQ_API_KEY=your_groq_api_key_here
   GROQ_MODEL_NAME=mixtral-8x7b-32768
   ```

## Usage

### Running the Voice Agent (Gemini)

```bash
python main.py
```

This will start the voice agent using Google Gemini Real-time API. The agent will:

- Listen for incoming calls
- Respond with a greeting
- Process voice input and generate responses
- Handle session lifecycle events

### Using Groq Model (Alternative)

```bash
python models/groq_model.py
```

This demonstrates using Groq as an alternative LLM provider.

## Project Structure

```
Voice-Agent-main/
├── main.py                    # Main voice agent implementation
├── requirements.txt           # Python dependencies
├── models/
│   └── groq_model.py         # Groq model integration example
└── README.md                  # This file
```

## Configuration

### Environment Variables

| Variable          | Description                          | Example              |
| ----------------- | ------------------------------------ | -------------------- |
| `GOOGLE_API_KEY`  | Google Gemini API authentication key | `sk-...`             |
| `GROQ_API_KEY`    | Groq API authentication key          | `gsk-...`            |
| `GROQ_MODEL_NAME` | Groq model to use                    | `mixtral-8x7b-32768` |

## Key Components

### MyVoiceAgent Class

- Defines agent behavior and personality
- Handles message processing
- Manages session lifecycle (on_enter, on_exit events)

### Pipeline

- Integrates the LLM with audio processing
- Manages real-time voice synthesis

### AgentSession

- Manages the voice conversation session
- Handles participant connection and media

## Dependencies

- **videosdk-agents** - Voice agent framework
- **videosdk-plugins-google** - Google Gemini integration
- **python-dotenv** - Environment variable management
- **langchain-groq** - Groq LLM integration (optional)

## Customization

To customize the agent's behavior, modify the following:

1. **Instructions** - Change the system prompt in `MyVoiceAgent.__init__()`
2. **Voice** - Modify the `voice` parameter in `GeminiLiveConfig`
3. **Greeting** - Update the message in `on_enter()` method
4. **Response Logic** - Modify the `on_message()` method

## Troubleshooting

- **API Key Error**: Ensure your `.env` file is in the project root and contains valid API keys
- **Connection Issues**: Check your internet connection and VideoSDK credentials
- **Audio Issues**: Verify your microphone and speaker are properly configured

## Future Improvements

- Enhanced error handling and retry logic
- Comprehensive logging system
- Database integration for call history
- Multi-language support
- Custom voice and personality profiles
- Integration with additional LLM providers

## Real-World Implementation

⚡ **If you want to learn how this system is used in real-world projects and production environments, please contact me directly.**

This includes:

- Production deployment strategies
- Performance optimization techniques
- Scaling considerations
- Integration with existing systems
- Security best practices
- Real-world use cases and case studies

## Contact

For questions, improvements, additional information, or real-world implementation details about this project, **please reach out to the developer**.

---

💬 **Contact for:**

- Real-world usage examples and best practices
- Production deployment guidance
- Custom implementations for your use case
- Questions about extending the system
- Suggestions and improvements

## License

This is sample code provided as-is. Modify and use as needed for your project.

---

**Last Updated:** April 15, 2026
