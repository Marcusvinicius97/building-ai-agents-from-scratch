# Building AI Agents from Scratch — Weather Agent & The Daily Dish Chatbot

Multi-agent systems built in plain Python, without agent frameworks.

This repository is part of my continuing study of AI agents. I already work with the topic, and I used the hands-on lab **Building AI Agents from Scratch with Python** (IBM Skills Network) to review the fundamentals and practice implementing multi-agent systems from the ground up, without relying on frameworks.

## 1. Weather AI Agent

Three agents work in sequence:

- **WeatherRetrievalAgent** — fetches live weather data from the OpenWeather API
- **MemoryAgent** — stores past queries
- **ResponseAgent** — turns the data into a readable sentence

## 2. The Daily Dish Chatbot

A customer-service chatbot that answers questions using the restaurant's FAQ PDF:

- **QueryUnderstandingAgent** — extracts keywords and intent from the question, with synonym expansion
- **DocumentRetrievalAgent** — finds the most relevant FAQ entry with TF-IDF + cosine similarity (with stemming)
- **ChatMemoryAgent** — keeps the recent conversation history
- **ChatResponseAgent** — builds the final reply, with a fallback when no answer is found

## Setup

```bash
pip install requests pypdf scikit-learn nltk numpy
```

Get a free API key at https://home.openweathermap.org/api_keys and save it as an environment variable:

```powershell
# Windows
setx WEATHER_API_KEY "your_key_here"
```

```bash
# macOS / Linux
export WEATHER_API_KEY="your_key_here"
```

Then open the notebook and run the cells in order. The FAQ PDF is downloaded automatically from the course server on the first run.

## Credits

- **Original lab:** *Building AI Agents from Scratch with Python* — IBM Skills Network. The lab description, notebook structure, the Weather Agent template and the FAQ PDF (*The Daily Dish*) belong to the original course material.
- **My work on top of the lab:**
  - Fixed the environment setup (package installation inside the notebook kernel and the `pypdf` import)
  - Moved the API key out of the code into an environment variable
  - Implemented the Daily Dish chatbot (Steps 3–8), which was left empty in the lab notebook
  - Kept the course PDF out of the repository; the notebook downloads it from the original source
- Developed with the help of an AI coding assistant (Claude).

Course material remains the property of its authors. This repository is shared for educational purposes.
