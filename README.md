# 🍳 Master Chef Agent

**An AI-powered culinary research team built with Google's Agent Development Kit (ADK).**  
Submission for the Google AI Agents Intensive Course — Capstone Project.

---

## 📖 The Pitch

In the fast-paced world of culinary arts, staying ahead of food trends, understanding flavor profiles, and designing menus can take hours of research. **Master Chef Agent** automates that work by orchestrating a team of specialized AI agents:

- Scouts the web for the latest ingredients and trends.  
- Analyzes findings for nutritional value and flavor compatibility.  
- Summarizes everything into a cohesive Executive Menu Plan.

Think of it as your personal AI culinary staff that produces actionable menu ideas and executive summaries.

---

## ⚙️ Architecture

This project demonstrates a **Multi-Agent System (MAS)** using a hierarchical workflow: Research → Analyze → Summarize.

### The Team (Agents)

- **🕵️ Researcher Agent (The Scout)**  
  **Role:** Searches the internet for real-time data on specific food topics (e.g., "Molecular Gastronomy trends 2025").  
  **Tool:** Google Search (Simulated/Real).  
  **Goal:** Gather raw intelligence.

- **🧐 Analyzer Agent (The Critic)**  
  **Role:** Takes the raw research and identifies patterns, pros/cons, and key insights.  
  **Tool:** `analyze_data` (custom tool).  
  **Goal:** Refine data into actionable insights.

- **👨‍🍳 Summarizer Agent (The Chef)**  
  **Role:** Synthesizes the analysis into a final output (e.g., a menu or executive summary).  
  **Tool:** None (pure generation).  
  **Goal:** Create the final product for the user.

### Workflow

1. Researcher collects raw sources and trends.  
2. Analyzer extracts patterns, nutritional notes, and flavor compatibility.  
3. Summarizer composes a final Executive Menu Plan and concise action items.

---

## 🧩 Key Technical Features

- **Google ADK Framework** — built with the `google-adk` Python SDK.  
- **Gemini 1.5 Pro / Flash** — powers the agents' reasoning.  
- **InMemorySessionService** — manages conversation state & history.  
- **Asynchronous Execution** — uses `runner.run_async` to orchestrate tools non-blockingly.  
- **Custom Tools** — Python functions wrapped for automatic tool schema generation (e.g., `google_search`, `analyze_data`).

---

## 🛠️ Installation & Setup

### Prerequisites

- Python **3.10+**
- A Google Cloud Project with **Gemini API** access (or local simulation for demos)

### 1) Clone the repo

```bash
git clone https://github.com/Vagventure/Master-Chef-Agent---Google-Ai-Agents-Course.git
cd Master-Chef-Agent---Google-Ai-Agents-Course
```

### 2) Create and activate virtual environment
```
python -m venv venv
source venv/bin/activate        # macOS / Linux
# On Windows:
# venv\Scripts\activate
```

### 3) Install Dependencies
```
pip install -r requirements.txt
# or:
pip install google-adk python-dotenv
```

### 4) Configure Environment
```
GEMINI_API_KEY=your_actual_api_key_here
# Optional:
# GOOGLE_ADK_PROJECT_ID=your-project-id
```

### 5) Usage
```
python multi_agent_research.py
