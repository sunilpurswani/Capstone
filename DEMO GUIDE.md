# Demo Guide

This guide covers the main ways to review and run the financial multi-agent system locally.

## Core Agents

The financial workflow includes several specialized agents under:

```text
streamlined-adapter/examples/domain_agents/
```

Key files:

- `financial_advisor_agent.py` — stock and market analysis
- `report_summarizer_agent.py` — structured report generation
- `intelligent_report_agent.py` — tool-enabled financial analysis and agent coordination
- `risk_assessment_agent.py` — investment risk analysis
- `web_ui.py` — web interface components

## Architecture

```text
User Request
     |
     v
Intelligent / Report Agent
     |
     |-- Market-data tools --> yfinance
     |
     |-- A2A communication --> Risk Assessment Agent
     |
     v
Financial Analysis
     |
     v
Structured Report
```

## Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/sunilpurswani/Capstone.git
cd Capstone
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

```bash
# macOS / Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create the environment variables required by the agents you plan to run:

```text
ANTHROPIC_API_KEY=your-api-key
MONGODB_URI=your-mongodb-connection-string
```

Some components may not require MongoDB when telemetry or persistence is disabled.

## Running the Financial Advisor and Report Summarizer

Open separate terminals and navigate to:

```bash
cd streamlined-adapter/examples/domain_agents
```

Run the Financial Advisor Agent:

```bash
python financial_advisor_agent.py
```

Run the Report Summarizer Agent:

```bash
python report_summarizer_agent.py
```

Typical local ports are:

- Financial Advisor: `6001`
- Report Summarizer: `6002`

## Example Requests

Financial Advisor:

```bash
curl -X POST http://localhost:6001/a2a \
  -H "Content-Type: application/json" \
  -d '{"content":{"text":"single: AAPL 3mo","type":"text"},"role":"user","conversation_id":"local-test"}'
```

Report Summarizer:

```bash
curl -X POST http://localhost:6002/a2a \
  -H "Content-Type: application/json" \
  -d '{"content":{"text":"summarize: AAPL,GOOGL 3mo","type":"text"},"role":"user","conversation_id":"local-test"}'
```

## Risk Assessment Agent

The Risk Assessment Agent is designed to receive stock information from another agent through A2A communication and return a specialized risk analysis.

Run it from the domain-agents directory:

```bash
python risk_assessment_agent.py
```

Its default local port is `6004`.

## Quick Demo

The repository includes additional demo and test files:

```text
demo.py
demo_agents.sh
test.py
streamlined-adapter/examples/domain_agents/test_financial_system.py
```

These can be used to inspect the end-to-end flow and validate local agent behavior.

## Deployment

The repository contains scripts used during cloud-deployment experiments, including:

```text
deploy-to-linode-test.sh
my-nanda-agents-config.json
```

Deployment scripts may require environment-specific configuration before reuse.

## Notes

- External API keys are not stored in the repository.
- Market-data requests require internet access.
- Agent ports can be changed through the corresponding configuration or environment variables.
- Cloud endpoints used during development are not assumed to remain permanently available.

This project is for educational and analytical purposes only and is not financial advice.
