# Intelligent Stock Market Analyzer Agent

A collaborative capstone project focused on building a multi-agent financial intelligence system for stock analysis, investment reporting, and risk assessment.

The system combines real-time market data, large language models, specialized AI agents, MCP-style tool use, and agent-to-agent communication to answer natural-language financial questions and generate structured analysis.

## Project Overview

The project explores how multiple specialized agents can work together instead of relying on a single model for every task.

The financial workflow includes:

- retrieving stock market data with `yfinance`
- analyzing companies and market performance
- generating structured investment reports
- evaluating investment risk with a specialized risk agent
- coordinating agents through A2A communication
- exposing agent functionality through web/API interfaces
- supporting local and cloud deployment

## System Architecture

```text
User Request
     |
     v
Intelligent / Report Agent
     |
     |-- MCP-style tool calls --> Market Data Tools --> yfinance
     |
     |-- A2A request ----------> Risk Assessment Agent
     |
     v
Financial Analysis + Risk Assessment
     |
     v
Structured Investment Report
```

The repository also contains the Financial Advisor and Report Summarizer agents used during earlier stages of the project.

## Main Agents

### Financial Advisor Agent
Analyzes individual stocks and market data using financial metrics and historical price information.

### Report Summarizer Agent
Transforms financial analysis into structured, readable investment reports.

### Intelligent Report Agent
Coordinates market-data tools and specialized agents to produce more complete financial analysis from natural-language requests.

### Risk Assessment Agent
Provides a separate risk-analysis layer for investment decisions, including risk factors, volatility considerations, risk scoring, and mitigation suggestions.

## Technologies

| Area | Technology |
|---|---|
| Language | Python |
| LLM | Anthropic Claude |
| Market Data | yfinance |
| Agent Communication | python-a2a / A2A |
| Tool Integration | MCP-style tool calling |
| API / Web Layer | Flask |
| Data Processing | pandas, NumPy |
| Database / Telemetry | MongoDB Atlas |
| Cloud Deployment | Linode |

## Key Project Files

```text
Capstone/
├── README.md
├── DEMO GUIDE.md
├── demo.py
├── demo_agents.sh
├── deploy-to-linode-test.sh
├── my-nanda-agents-config.json
├── requirements.txt
└── streamlined-adapter/
    ├── examples/
    │   └── domain_agents/
    │       ├── financial_advisor_agent.py
    │       ├── report_summarizer_agent.py
    │       ├── intelligent_report_agent.py
    │       ├── risk_assessment_agent.py
    │       └── web_ui.py
    └── nanda_core/
        └── core/
```

## Example Queries

The agents can handle requests such as:

```text
single: AAPL 3mo
```

```text
summarize: AAPL,GOOGL 3mo
```

The intelligent agent can also work with natural-language questions about stock performance, comparisons, and investment risk.

## Running the Project

### Requirements

- Python 3.10+
- Anthropic API key
- Internet access for market data
- MongoDB Atlas or a local MongoDB instance for components that use telemetry or persistence

### Setup

```bash
git clone https://github.com/sunilpurswani/Capstone.git
cd Capstone

python -m venv .venv
```

Activate the environment:

```bash
# macOS / Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Create the required environment variables before starting agents that use external services:

```text
ANTHROPIC_API_KEY=your-api-key
MONGODB_URI=your-mongodb-connection-string
```

For agent-specific commands and testing examples, see [`DEMO GUIDE.md`](./DEMO%20GUIDE.md).

## What the Project Demonstrates

- multi-agent system design
- agent-to-agent communication
- LLM integration
- real-time financial data integration
- API and tool orchestration
- risk-analysis workflows
- cloud deployment concepts
- financial data processing and reporting

## Project Context

This repository contains work from a collaborative capstone project. The system and codebase reflect team development, integration, testing, and experimentation across the project lifecycle.

The application is intended for educational and analytical exploration only and should not be treated as professional financial advice.

## Author

Sunil Purswani
