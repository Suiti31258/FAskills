# Financial-Researcher MVP: Ralph Loop Execution Plan

## Overview

Building the financial-researcher skill using Ralph Loop methodology.
Each phase has clear success criteria and completion promises.

---

## Phase 1: Foundation (Rounds 1-4)

### Round 1: Project Structure
**Focus:** Create complete directory structure with placeholder files
**Success:** All directories and empty files exist
**Completion Promise:** `<promise>STRUCTURE COMPLETE</promise>`

Create:
```
financial-researcher/
├── SKILL.md
├── experts/
│   ├── warren_buffett.md
│   ├── ben_graham.md
│   ├── peter_lynch.md
│   ├── cathie_wood.md
│   ├── george_soros.md
│   ├── ray_dalio.md
│   └── michael_burry.md
├── references/
│   └── DRIVER_Best_Practices.md
├── mcp/
│   ├── financialdatasets-mcp/
│   │   ├── pyproject.toml
│   │   ├── src/
│   │   │   └── server.py
│   │   └── README.md
│   └── tavily-mcp/
│       ├── pyproject.toml
│       ├── src/
│       │   └── server.py
│       └── README.md
├── templates/
│   ├── expert_output.json
│   └── consolidated_report.md
└── .env.example
```

### Round 2: Core Skill Framework
**Focus:** Write SKILL.md with complete orchestration logic
**Success:** SKILL.md has full DRIVER workflow, mode selection, expert dispatch
**Completion Promise:** `<promise>SKILL FRAMEWORK COMPLETE</promise>`

### Round 3: Expert Template System
**Focus:** Create expert base template that all 7 gurus will follow
**Success:** Template in templates/ with all required sections
**Completion Promise:** `<promise>EXPERT TEMPLATE COMPLETE</promise>`

### Round 4: Output Schema Definition
**Focus:** Define JSON schema and markdown template for outputs
**Success:** Both templates complete with all fields documented
**Completion Promise:** `<promise>OUTPUT SCHEMA COMPLETE</promise>`

---

## Phase 2: Data Layer - MCP Servers (Rounds 5-10)

### Round 5: financialdatasets-mcp Structure
**Focus:** pyproject.toml, dependencies, server skeleton with tool stubs
**Success:** Server starts, tools defined but return mock data
**Completion Promise:** `<promise>FD MCP SKELETON COMPLETE</promise>`

### Round 6: financialdatasets-mcp Financial Tools
**Focus:** Implement get_income_statements, get_balance_sheets, get_cash_flows, get_financial_metrics
**Success:** All 4 tools make real API calls, handle errors
**Completion Promise:** `<promise>FD FINANCIAL TOOLS COMPLETE</promise>`

### Round 7: financialdatasets-mcp Market Tools
**Focus:** Implement get_prices, get_market_cap, get_insider_trades
**Success:** All 3 tools work with real API
**Completion Promise:** `<promise>FD MARKET TOOLS COMPLETE</promise>`

### Round 8: financialdatasets-mcp SEC Filing Tools
**Focus:** Implement get_10k_items, get_10q_items, get_8k_items, get_13f_holdings
**Success:** Smart item extraction working, returns relevant sections only
**Completion Promise:** `<promise>FD SEC TOOLS COMPLETE</promise>`

### Round 9: tavily-mcp Implementation
**Focus:** Full tavily-mcp server with search_finance, search_news, search_general
**Success:** All tools work with topic filtering and time ranges
**Completion Promise:** `<promise>TAVILY MCP COMPLETE</promise>`

### Round 10: MCP Integration Test
**Focus:** Test both servers together, verify all tools work
**Success:** Can fetch complete data set for a real ticker (AAPL)
**Completion Promise:** `<promise>MCP LAYER COMPLETE</promise>`

---

## Phase 3: Expert Prompts (Rounds 11-16)

### Round 11: Warren Buffett Expert
**Focus:** Complete buffett prompt with all sections from design
**Success:** Prompt includes moat analysis, owner earnings, intrinsic value, forward thesis, holdings integration
**Completion Promise:** `<promise>BUFFETT EXPERT COMPLETE</promise>`

### Round 12: Ben Graham Expert
**Focus:** Complete graham prompt
**Success:** Mr. Market, margin of safety calc, asset-based valuation, earnings power
**Completion Promise:** `<promise>GRAHAM EXPERT COMPLETE</promise>`

### Round 13: Peter Lynch + Cathie Wood Experts
**Focus:** Both growth-focused experts
**Success:** Lynch PEG/story framework, Wood disruption/TAM framework
**Completion Promise:** `<promise>GROWTH EXPERTS COMPLETE</promise>`

### Round 14: George Soros Expert
**Focus:** Reflexivity framework complete
**Success:** Feedback loops, boom-bust cycle positioning, macro regime, narrative analysis
**Completion Promise:** `<promise>SOROS EXPERT COMPLETE</promise>`

### Round 15: Ray Dalio Expert
**Focus:** Cycles and history framework
**Success:** Debt cycle analysis, historical templates, stress testing, principles
**Completion Promise:** `<promise>DALIO EXPERT COMPLETE</promise>`

### Round 16: Michael Burry Expert
**Focus:** Forensic and bear case framework
**Success:** Revenue/earnings quality forensics, bear case construction, contrarian signals
**Completion Promise:** `<promise>BURRY EXPERT COMPLETE</promise>`

---

## Phase 4: Orchestration (Rounds 17-19)

### Round 17: Data Routing Logic
**Focus:** Expert data requirements matrix, union calculation, subset routing
**Success:** Each expert gets exactly what they need, fetched once
**Completion Promise:** `<promise>DATA ROUTING COMPLETE</promise>`

### Round 18: Subagent Dispatch System
**Focus:** Task tool integration for parallel expert execution
**Success:** Can spawn all 7 experts in parallel with correct data
**Completion Promise:** `<promise>DISPATCH SYSTEM COMPLETE</promise>`

### Round 19: Mode Selection & DRIVER Flow
**Focus:** Quick vs Full mode, visible DRIVER stage markers
**Success:** Both modes work, stages print correctly
**Completion Promise:** `<promise>ORCHESTRATION COMPLETE</promise>`

---

## Phase 5: Integration (Rounds 20-22)

### Round 20: Consolidation Logic
**Focus:** Aggregate 7 expert outputs without losing individual insights
**Success:** Signal tally, confidence weighting, agreement matrix, risk union
**Completion Promise:** `<promise>CONSOLIDATION COMPLETE</promise>`

### Round 21: Output Formatting
**Focus:** Generate both markdown report and JSON file
**Success:** Beautiful markdown displayed, complete JSON saved
**Completion Promise:** `<promise>OUTPUT FORMAT COMPLETE</promise>`

### Round 22: End-to-End Test
**Focus:** Full analysis of AAPL through entire pipeline
**Success:** Complete report generated with all 7 expert analyses
**Completion Promise:** `<promise>MVP COMPLETE</promise>`

---

## Ralph Loop Commands

### To start each phase:

**Phase 1:**
```
/ralph-loop "Execute RALPH_EXECUTION_PLAN.md Phase 1 Rounds 1-4. Create foundation structure. Check off completed rounds in this file. Output <promise>PHASE 1 COMPLETE</promise> when all 4 rounds done." --max-iterations 6 --completion-promise "PHASE 1 COMPLETE"
```

**Phase 2:**
```
/ralph-loop "Execute RALPH_EXECUTION_PLAN.md Phase 2 Rounds 5-10. Build MCP servers. Check off completed rounds. Output <promise>PHASE 2 COMPLETE</promise> when done." --max-iterations 10 --completion-promise "PHASE 2 COMPLETE"
```

**Phase 3:**
```
/ralph-loop "Execute RALPH_EXECUTION_PLAN.md Phase 3 Rounds 11-16. Create expert prompts. Check off completed rounds. Output <promise>PHASE 3 COMPLETE</promise> when done." --max-iterations 10 --completion-promise "PHASE 3 COMPLETE"
```

**Phase 4:**
```
/ralph-loop "Execute RALPH_EXECUTION_PLAN.md Phase 4 Rounds 17-19. Build orchestration. Check off completed rounds. Output <promise>PHASE 4 COMPLETE</promise> when done." --max-iterations 6 --completion-promise "PHASE 4 COMPLETE"
```

**Phase 5:**
```
/ralph-loop "Execute RALPH_EXECUTION_PLAN.md Phase 5 Rounds 20-22. Integration and test. Check off completed rounds. Output <promise>MVP COMPLETE</promise> when done." --max-iterations 6 --completion-promise "MVP COMPLETE"
```

---

## Progress Tracking

### Phase 1: Foundation
- [x] Round 1: Project Structure
- [x] Round 2: Core Skill Framework
- [x] Round 3: Expert Template System
- [x] Round 4: Output Schema Definition

### Phase 2: Data Layer
- [x] Round 5: financialdatasets-mcp Structure
- [x] Round 6: FD Financial Tools
- [x] Round 7: FD Market Tools
- [x] Round 8: FD SEC Filing Tools
- [x] Round 9: tavily-mcp Implementation
- [x] Round 10: MCP Integration Test

### Phase 3: Expert Prompts
- [x] Round 11: Warren Buffett
- [x] Round 12: Ben Graham
- [x] Round 13: Peter Lynch + Cathie Wood
- [x] Round 14: George Soros
- [x] Round 15: Ray Dalio
- [x] Round 16: Michael Burry

### Phase 4: Orchestration
- [x] Round 17: Data Routing Logic
- [x] Round 18: Subagent Dispatch System
- [x] Round 19: Mode Selection & DRIVER Flow

### Phase 5: Integration
- [x] Round 20: Consolidation Logic
- [x] Round 21: Output Formatting
- [x] Round 22: End-to-End Test

---

## Quality Gates

Before marking any round complete, verify:

1. **Code compiles/parses** - No syntax errors
2. **Files are complete** - No TODO placeholders left
3. **Matches design spec** - Refer to ClaudeCodeSkillDevelopmentPlan.md
4. **Self-contained** - Each piece works independently
5. **Documented** - Comments explain non-obvious logic

---

## Context Files for Ralph

Each Ralph iteration should reference:
- This file (RALPH_EXECUTION_PLAN.md)
- ClaudeCodeSkillDevelopmentPlan.md (original requirements)
- DRIVER/DRIVER_Best_Practices_Guide_v3-BriefCheckList.md (DRIVER framework)
- Any previously created files in financial-researcher/

---

## Notes

- Ralph sees its previous work in the files
- Each iteration builds on what exists
- Check off rounds as completed
- If stuck, add notes in this file for next iteration
- Quality over speed - better to do fewer rounds well
