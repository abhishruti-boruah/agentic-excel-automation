# agentic-excel-automation
An Agentic AI system leveraging the ReAct framework and LangChain to automate Excel data functions (filtering and sorting) via natural language instructions.
# Agentic-DF: Natural Language Driven Autonomous Agent for Excel Manipulation

An intelligent, agentic AI system that enables users to manipulate Excel sheets (filtering, sorting, and processing data) using intuitive natural language commands instead of writing complex code or macros.

## 🚀 Key Features
* **Natural Language Interface:** Translate user intent into precise data manipulations.
* **ReAct Framework Implementation:** Leverages a Reasoning and Acting loop via LLMs to handle state dynamically.
* **Safe Local Tool Execution:** Instead of feeding massive raw data directly into the LLM context, the agent intelligently triggers isolated Python `pandas` tools to execute files locally.
* **Production-Ready Architecture:** Designed and built entirely inside a cloud-hosted GitHub Codespace container environment.

---

## 🏗️ System Architecture

The project operates on the **ReAct (Reasoning + Acting)** paradigm. When a user inputs a query, the system loops through the following states:

1. **Thought:** The LLM analyzes the request and breaks it down into required operations.
2. **Action:** The LLM selects the optimal tool (`FilterExcel` or `SortExcel`) and generates the precise arguments needed.
3. **Observation:** The Python backend executes the tool, saves the updated Excel spreadsheet, and returns a success confirmation to the agent.

---

## 🛠️ Tech Stack & Dependencies
* **Orchestration:** LangChain (ReAct Agent Workflow)
* **LLM Engine:** OpenAI `gpt-4o-mini` (or alternative specified model)
* **Data Core:** Python `pandas`, `openpyxl`
* **Environment:** GitHub Codespaces (Cloud container deployment)

---

## 📁 File Structure
```text
├── .env                  # Secret API credentials (ignored by git)
├── requirements.txt      # Project library dependencies
├── agent.py              # Main ReAct controller and agent loop
├── tools.py              # Python-pandas tool implementations
├── mock_data.xlsx        # Sample dataset for live demonstration
└── README.md             # Project documentation
