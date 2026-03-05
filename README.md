# Google's Agent Development Kit (ADK) BI Agent with Gradio

![Python Version](https://img.shields.io/badge/python-3.12-blue.svg)
![uv](https://img.shields.io/badge/uv-managed-430f8e.svg?style=flat&logo=python&logoColor=white)
![Gradio Version](https://img.shields.io/badge/gradio-6.1.0-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

---

## Context

This project demonstrates how to build a **sequential agent pipeline** using Google's Agent Development Kit (ADK).

The system:

1. Converts natural language questions into SQL queries  
2. Executes queries against Microsoft SQL Server  
3. Generates visualizations  
4. Produces AI-powered explanations using Google Gemini  

It can be accessed through:

- ADK Web interface  
- Gradio Web interface  

---

## Architecture Overview

The system follows a sequential agent pipeline design:

```
User Query
   ↓
NL → SQL Agent (Gemini)
   ↓
SQL Executor
   ↓
Business Intelligence Service
   ↓
Visualization + Explanation
```

### Key Design Principles

- Modular agent design  
- Separation of concerns  
- Reusable tools  
- Configurable environment  
- Reproducible setup with uv  

---

## Project Structure

The project follows the ADK directory structure:

```
gradio-adk-agent/
├── bi_agent/              # Agent package
│   ├── __init__.py
│   ├── agent.py           # Main agent definitions
│   ├── tools.py           # Custom tool definitions
│   ├── bi_service.py      # Business Intelligence service layer
│   ├── db_config.py       # Database configuration
│   ├── sql_executor.py    # SQL execution utilities
│   └── .env               # API keys and credentials (not committed)
├── app.py                 # Gradio web interface
├── pyproject.toml         # Project dependencies
└── README.md
```

---

## Prerequisites

- Python 3.12  
- uv (Python package & environment manager)  
- Google API key from Google AI Studio  
- Microsoft SQL Server access  

---

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/ChronicleOfZealvy/Agentic_AI_Project.git
cd gradio-adk-agent
```

### 2. Install dependencies

```bash
uv sync
```

This will create a virtual environment and install all dependencies.

---

### 3. Configure Environment Variables

Rename `.example.env` to `.env` inside the `bi_agent` folder and fill in:

```
# Google API Key
GOOGLE_API_KEY=your_gemini_api_key_here

# SQL Server Configuration
MSSQL_SERVER=your_server_address
MSSQL_DATABASE=your_database_name
MSSQL_USERNAME=your_username
MSSQL_PASSWORD=your_password
```

The `.env` file is excluded via `.gitignore` to protect credentials.

---

## Running the Project

### Option 1: ADK Web Interface

```bash
uv run adk web . --port 8000
```

Open:

```
http://127.0.0.1:8000
```

---

### Option 2: Gradio Interface

```bash
uv run app.py
```

Open:

```
http://127.0.0.1:7860
```

---

## Python Management with uv

Add new dependencies:

```bash
uv add <package-name>
```

Run project:

```bash
uv run
```

---

## Features

- Natural language to SQL conversion  
- Secure SQL execution layer  
- Business Intelligence service abstraction  
- Automated visualization generation  
- AI-generated analytical explanations  
- Dual interface support (ADK + Gradio)  
- Reproducible environment with uv  

---

## Summary

This project demonstrates:

- Agent-based system design  
- Sequential pipeline architecture  
- LLM tool integration  
- Database connectivity  
- Web UI deployment  
- Clean modular structure  

Suitable for:

- AI Engineering coursework  
- Business Intelligence system demonstrations  
- Portfolio projects  
- Agentic system experimentation  

---
