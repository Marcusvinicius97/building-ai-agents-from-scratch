# Building AI Agents from Scratch — Weather Agent & The Daily Dish Chatbot

Multi-agent systems built in plain Python, without agent frameworks.

## 1. Weather AI Agent

Three agents work in sequence:

- **WeatherRetrievalAgent** — fetches live weather data from the OpenWeather API
- **MemoryAgent** — stores past queries
- **ResponseAgent** — turns the data into a readable sentence

## 2. The Daily Dish Chatbot

A customer-service chatbot that answers questions using the restaurant's FAQ PDF (`The_Daily_Dish_FAQ.pdf`):

- **QueryUnderstandingAgent** — extracts keywords and intent from the question
- **DocumentRetrievalAgent** — finds the most relevant FAQ entry with TF-IDF + cosine similarity
- **ChatMemoryAgent** — keeps the recent conversation history
- **ChatResponseAgent** — builds the final reply

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

Then open the notebook and run the cells in order.
