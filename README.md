
# NewsNinja 🗞️🤖

**NewsNinja** is an AI-powered news aggregator and audio summarizer that transforms the noise of the internet into concise, personalized audio briefings. By combining real-time news scraping with raw social sentiment from Reddit, this system provides a 360-degree view of any topic in under two minutes.

I developed this project to solve the "tab overload" problem, automating the tedious process of cross-referencing news headlines with public opinion.

---

## 🧠 The Concept

Instead of just reading headlines, NewsNinja acts as a digital journalist. It performs three core tasks:

1. **Scraping:** Silently scouts reputable news sources and real-time Reddit threads.
2. **Synthesis:** Uses AI agents to analyze the news and public reactions to extract the "truth" behind the headlines.
3. **Broadcasting:** Generates a professional, high-quality audio briefing that you can listen to on the go.

---

## 🏗️ Technical Architecture

This project is built as a distributed system, separating the user interface from the heavy data-processing backend.

* **Frontend:** A clean, interactive **Streamlit** dashboard for managing topics and listening to briefings.
* **Backend:** A robust **FastAPI** server that manages the orchestration of AI agents.
* **Data Ingestion:** Utilizes advanced scraping infrastructure (Bright Data MCP) to bypass anti-bot measures and access live Reddit/news data.
* **Intelligence Layer:** Uses LLMs (Claude) for summarization and logic extraction.
* **Audio Generation:** Leverages **ElevenLabs API** for natural, human-sounding text-to-speech synthesis.

---

## 🚀 Key Features

* **Real-Time Data Access:** Bypasses standard scraping limitations to get the latest social sentiment from Reddit.
* **AI Agentic Workflow:** Uses agents to filter noise, summarize complex articles, and provide objective analysis.
* **Bite-Sized Audio:** Automatically converts text summaries into a 2-minute audio file.
* **Privacy-First:** Designed to handle data processing efficiently without unnecessary overhead.

---

## 🛠️ Tech Stack

* **Language:** Python 3.9+
* **Frameworks:** Streamlit (UI), FastAPI (Backend)
* **AI/Orchestration:** Anthropic API (Claude), ElevenLabs (TTS), Bright Data MCP
* **Environment Management:**`pipenv`

---

QUICK START

1. **Environment Setup:**
   Initialize your virtual environment and install dependencies:
   **Bash**

   ```
   pipenv install
   pipenv shell
   ```
2. **Configuration:**
   Create a `.env` file to manage your API keys (Anthropic, ElevenLabs, Bright Data):

```
cp .env.example .env
```

3. Configure your secrets in .env:

```
# Bright Data
BRIGHTDATA_MCP_KEY="your_mcp_api_key"
BROWSER_AUTH="your_browser_auth_token"

# ElevenLabs 
ELEVENLABS_API_KEY="your_text_to_speech_key"
```

4. Prepare Your Weapons (Bright Data Setup)

- Create MCP zone: https://brightdata.com/cp/zones
- Enable browser authentication
- Copy credentials to .env

---

RUNNING THE NINJA

First terminal (Backend):

```
pipenv run python backend.py
```

Second terminal (Frontend):

```
pipenv run streamlit run frontend.py
```

---

PROJECT STRUCTURE

```
.
├── frontend.py          # Streamlit UI
├── backend.py           # API & data processing  
├── utils.py             # UTILS  
├── news_scraper.py      # News Scraper  
├── reddit_scraper.py    # Reddit Scraper  
├── models.py            # Pydantic model
├── Pipfile              # Dependency scroll
├── .env.example         # Secret map template
└── requirements.txt     # Alternative dependency list
```

---

NOTES

- First scrape takes 15-20 seconds (good ninjas are patient)
- Reddit scraping uses real browser emulation via MCP
- Keep .env file secret (ninjas never reveal their tools)
