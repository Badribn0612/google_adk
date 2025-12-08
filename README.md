# Google ADK Learning Repository

This repository contains learning materials, examples, and implementations for Google ADK (Agent Development Kit). It includes a comprehensive 5-day AI agents course and various agent implementations demonstrating different capabilities.

## 📚 Overview

This repository serves as a learning resource for building AI agents using Google's Agent Development Kit. It covers topics ranging from basic agent creation to advanced concepts like agent architectures, tools, sessions, and memory management.

## 🗂️ Repository Structure

```
google_adk/
├── 5_day_ai_agents_course/     # Comprehensive 5-day course materials
│   ├── day-1a-from-prompt-to-action.ipynb
│   ├── day-1b-agent-architectures.ipynb
│   ├── day-2a-agent-tools.ipynb
│   ├── day-2b-agent-tools-best-practices.ipynb
│   ├── day-2b-excercise.ipynb
│   ├── day-3a-agent-sessions.ipynb
│   ├── day-3b-agent-memory.ipynb
│   └── day-3b-excercise.ipynb
├── agent_adk_docs/              # Documentation and examples
│   └── progressive_weather_bot.ipynb
├── multi_tool_agent/            # Multi-tool agent example
│   └── agent.py
└── my_agent/                    # Basic agent example
    └── agent.py
```

## 🚀 Getting Started

### Prerequisites

- Python 3.11+
- Google ADK installed
- Access to Google's Gemini models

### Installation

1. Clone this repository:
```bash
git clone <repository-url>
cd google_adk
```

2. Set up a virtual environment (recommended):
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install Google ADK:
```bash
pip install google-adk
```

4. Configure your Google Cloud credentials and API access as per [Google ADK documentation](https://google.github.io/adk-docs/).

## 📖 Course Materials

The `5_day_ai_agents_course/` directory contains a structured learning path:

- **Day 1**: Introduction to agents and architectures
  - From prompt to action
  - Agent architectures

- **Day 2**: Agent tools
  - Working with tools
  - Best practices
  - Exercises

- **Day 3**: Agent sessions and memory
  - Agent sessions
  - Memory management
  - Exercises

## 🤖 Example Agents

### 1. Basic Search Agent (`adk-streaming/app/google_search_agent/`)

A streaming agent that uses Google Search to answer questions:

```python
from google.adk.agents import Agent
from google.adk.tools import google_search

root_agent = Agent(
    name="basic_search_agent",
    model="gemini-2.5-flash-native-audio-preview-09-2025",
    description="Agent to answer questions using Google Search.",
    instruction="You are an expert researcher. You always stick to the facts.",
    tools=[google_search]
)
```

### 2. Multi-Tool Agent (`multi_tool_agent/`)

An agent that combines multiple tools (weather and time) to answer questions:

```python
from google.adk.agents import Agent

root_agent = Agent(
    name="weather_time_agent",
    model="gemini-2.5-flash-native-audio-preview-09-2025",
    description="Agent to answer questions about the time and weather in a city.",
    instruction="You are a helpful agent who can answer user questions about the time and weather in a city.",
    tools=[get_weather, get_current_time]
)
```

### 3. Simple Time Agent (`my_agent/`)

A basic agent that tells the current time in cities:

```python
from google.adk.agents.llm_agent import Agent

root_agent = Agent(
    model='gemini-2.5-flash',
    name='root_agent',
    description="Tells the current time in a specified city.",
    instruction="You are a helpful assistant that tells the current time in cities.",
    tools=[get_current_time]
)
```

## 📝 Usage

### Running Jupyter Notebooks

1. Start Jupyter Lab:
```bash
jupyter lab
```

2. Navigate to the course materials or examples and run the notebooks.

### Running Agent Scripts

Each agent directory contains an `agent.py` file that can be imported and used in your applications. Refer to the Google ADK documentation for deployment and integration instructions.

## 🔗 Resources

- [Google ADK Documentation](https://google.github.io/adk-docs/)
- [Supported Models for Streaming](https://google.github.io/adk-docs/get-started/streaming/quickstart-streaming/#supported-models)
- [Google ADK GitHub](https://github.com/google/adk)

## 📄 License

This repository is for educational purposes. Please refer to Google ADK's license terms for the SDK usage.

## 🤝 Contributing

This is a personal learning repository. Feel free to fork and adapt for your own learning journey!

## 📌 Notes

- The `google-adk/` directory appears to be a Python virtual environment and should not be committed to version control
- Make sure to configure your Google Cloud credentials before running any agents
- Model names may need to be updated based on the latest available models from Google

