# ClaudeCodeSkillDevelopmentPlan
## Drafted by Cinder and Gemini Pro


I want to create a professional-grade Claude Code Skill called "financial-researcher". 

# The idea is inspired by the repo of [virattt/dexter](https://github.com/virattt/dexter).

This skill must operationalize the DRIVER Framework and use the architecture patterns of the virattt/dexter repository.

STRICT CONSTRAINTS:
1. DO NOT use yfinance. Use Financialdatasets.ai for fundamentals and Tavily for search.
2. IMPLEMENT a multi-LLM validation pattern (using Gemini/OpenAI APIs for "second opinions" during validation).
3. FOLLOW the DRIVER logic for all reasoning.

Please create the directory `financial-researcher/` and the following 5 files.

### 1. The Core Instruction File
File Path: `financial-researcher/SKILL.md`
Content:
"""
---
name: financial-researcher
description: Professional-grade autonomous financial analyst. Integrates Financialdatasets.ai, Tavily, and multi-LLM cross-validation. Guided strictly by the DRIVER protocol.
---

# Professional Financial Research Skill (DRIVER + Dexter Architecture)

## 1. Operational Framework
You are the "Pilot-in-Command." You are forbidden from "vibes-based" analysis. You follow the DRIVER stages:

### Phase 1: DISCOVER (Research)
- **Primary Source:** Financialdatasets.ai (for income statements, balance sheets, cash flows).
- **Context Source:** Tavily API (for live market sentiment and macro news).
- **Rule:** If data is missing from Financialdatasets, explicitly flag it.

### Phase 2: REPRESENT (Plan)
- **Goal:** Draft a "Flight Plan."
- **Action:** State the financial hypothesis and the list of specific metrics you will compare.

### Phase 3: IMPLEMENT (Execute)
- **Action:** Run `scripts/financial_engine.py` to fetch structured data.
- **Rule:** Calculations must be performed in code, not via LLM arithmetic.

### Phase 4: VALIDATE (Cross-Model Review)
- **Action:** Use the `cross_validate` tool in the engine to send the synthesis to Gemini or OpenAI for a "red-team" critique before finalizing.

## 2. Tool Usage
Always call `scripts/financial_engine.py` with appropriate API keys for:
- Tavily (Search)
- Financialdatasets (Financials)
- Gemini/OpenAI (Validation)
"""

### 2. The Brain (Protocol Definition)
File Path: `financial-researcher/references/DRIVER_Best_Practices.md`
(Claude: Please copy the content of the uploaded 'DRIVER_Best_Practices_Guide_v3-BriefCheckList.md' here.)

### 3. The Professional Engine (The "Hands")
File Path: `financial-researcher/scripts/financial_engine.py`
Content:
"""
import os
import sys
import json
import requests

def fetch_financials(ticker):
    # Endpoint for financialdatasets.ai
    api_key = os.getenv("FINANCIAL_DATASETS_API_KEY")
    url = f"https://api.financialdatasets.ai/financials/standardized?ticker={ticker}"
    headers = {"X-API-KEY": api_key}
    response = requests.get(url, headers=headers)
    return response.json()

def search_market_context(query):
    # Endpoint for Tavily
    api_key = os.getenv("TAVILY_API_KEY")
    payload = {"api_key": api_key, "query": query, "search_depth": "advanced"}
    response = requests.post("https://api.tavily.com/search", json=payload)
    return response.json()

def cross_validate(synthesis, model_provider="gemini"):
    # Pattern for calling Gemini/OpenAI for a second opinion
    # Implements the 'Validator' agent role from Dexter
    api_key = os.getenv(f"{model_provider.upper()}_API_KEY")
    # Logic to send the analysis to the external LLM for critique...
    return "Validation response placeholder"

if __name__ == "__main__":
    if len(sys.argv) < 3: sys.exit(1)
    cmd, val = sys.argv[1], sys.argv[2]
    if cmd == "financials": print(json.dumps(fetch_financials(val)))
    elif cmd == "search": print(json.dumps(search_market_context(val)))
"""

### 4. Dependency Management
File Path: `financial-researcher/scripts/requirements.txt`
Content:
"""
requests
python-dotenv
"""

### 5. API Key Template
File Path: `financial-researcher/.env.example`
Content:
"""
TAVILY_API_KEY=
FINANCIAL_DATASETS_API_KEY=
GEMINI_API_KEY=
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
"""

### 6. package management

use uv to manage Python versions, packages, environments, and dependencies.

### 7. API keys

API keys are in the .env file. DO NOT commit the .env file to GitHub or share it with anyone.

