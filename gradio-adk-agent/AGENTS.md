## Context

This project demonstrates how to build a **sequential agent pipeline** using **Google's Agent Development Kit (ADK)** with a **Gradio web interface**.

The system converts natural language questions into SQL queries, executes them on a database, and returns analytical results with visualizations and explanations.

The project can be run using either the **ADK web interface** or the **Gradio interface**. Both commands should be executed from the **`gradio-adk-agent` directory**.

---

## Agent Architecture

The system is implemented using a **sequential agent orchestration design**.

The main components are:

* **Root Agent** – orchestrates the workflow and delegates tasks.
* **BI Unified Agent** – generates SQL queries using schema information.
* **Insight Agent** – produces visualizations and analytical explanations.

The BI agent interacts with the database using two controlled tools:

* `get_database_schema`
* `execute_sql_and_format`

This design separates orchestration, SQL generation, and analytical interpretation into modular components.

---

## Project Structure

The repository structure is organized as follows:

```
.
├── assets/                        # Architecture diagrams
│   ├── Workflow.png
│   └── root_agent.png
│
├── gradio-adk-agent/              # Main ADK project
│   ├── bi_agent/                  # Agent package
│   │   ├── __init__.py
│   │   ├── agent.py               # Agent definitions
│   │   ├── tools.py               # Custom tools
│   │   ├── bi_service.py          # Business Intelligence service
│   │   ├── db_config.py           # Database configuration
│   │   ├── sql_executor.py        # SQL execution utilities
│   │   └── .env.example           # Environment variable template
│   │
│   ├── app.py                     # Gradio web interface
│   ├── AGENTS.md                  # Prompt templates
│   ├── pyproject.toml             # Project dependencies
│   └── uv.lock                    # Reproducible environment
│
├── README.md
└── Short Technical Report.md
```

---

## Running the Project

Navigate to the project directory:

```bash
cd gradio-adk-agent
```

### Option 1: ADK Web Interface

```bash
uv run adk web . --port 8000
```

This launches the ADK web interface at:

```
http://127.0.0.1:8000
```

### Option 2: Gradio Interface

```bash
uv run app.py
```

This launches the Gradio interface at:

```
http://127.0.0.1:7860
```

---

## Python Management with uv

The project environment is managed using **uv**.

To add a package:

```
uv add <package-name>
```

To run Python commands within the environment:

```
uv run <command>
```
