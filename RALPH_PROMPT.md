# Financial-Researcher MVP Build Prompt

## Your Mission

You are building the `financial-researcher` Claude Code skill - a professional-grade autonomous financial analyst that leverages 7 legendary investor perspectives.

## Context Files (Read These)

1. **RALPH_EXECUTION_PLAN.md** - Round-by-round plan with checkboxes
2. **ClaudeCodeSkillDevelopmentPlan.md** - Original requirements
3. **DRIVER/DRIVER_Best_Practices_Guide_v3-BriefCheckList.md** - DRIVER methodology

## Current State Assessment

Each iteration, you MUST:

1. **Check progress** - Read RALPH_EXECUTION_PLAN.md, see what's checked off
2. **Identify current round** - Find the first unchecked round
3. **Review existing work** - Read files already created in financial-researcher/
4. **Execute current round** - Complete ALL requirements for that round
5. **Mark complete** - Update RALPH_EXECUTION_PLAN.md checkbox
6. **Assess next** - If more rounds in current phase, continue; if phase done, output promise

## Quality Standards

### For Every File Created:

**Skill files (.md):**
- Complete YAML frontmatter (name, description)
- No placeholder text - fully written content
- Clear section headers
- Actionable instructions

**Python files (.py):**
- Type hints on all functions
- Docstrings explaining purpose
- Error handling with meaningful messages
- Async where appropriate for MCP

**Config files (pyproject.toml):**
- All dependencies specified with versions
- Proper metadata (name, version, description)
- Entry points configured

### For Expert Prompts:

Each guru prompt MUST include:
1. **Philosophy section** - Their investment worldview
2. **Analysis framework** - Specific criteria they evaluate
3. **Data requirements** - What data this expert needs
4. **Output format** - Exact JSON structure expected
5. **Forward-looking section** - Bold predictions, timelines, price targets
6. **Holdings integration** - How to incorporate their 13-F data
7. **Voice/tone guidance** - How this guru speaks (unfiltered, internal use)

### For MCP Servers:

Each tool MUST:
1. Have clear input schema with descriptions
2. Handle API errors gracefully
3. Return structured, typed responses
4. Include rate limiting awareness
5. Log meaningful debug info

## The 7 Gurus

| Guru | Focus | 13-F Source |
|------|-------|-------------|
| Warren Buffett | Moat, intrinsic value, owner earnings | Berkshire Hathaway |
| Ben Graham | Margin of safety, asset values | Historical (deceased) |
| Peter Lynch | GARP, understand the business | Historical (retired) |
| Cathie Wood | Disruption, TAM, 5-year vision | ARK Invest (daily!) |
| George Soros | Reflexivity, macro, sentiment loops | Soros Fund Mgmt |
| Ray Dalio | Cycles, history, debt analysis | Bridgewater |
| Michael Burry | Forensic, bear case, contrarian | Scion Asset Mgmt |

## Output Structure

**Displayed to user:** Rich markdown with all 7 analyses preserved
**Saved to file:** JSON at ./reports/{ticker}_{date}.json

## Key Design Decisions (Do Not Deviate)

1. **Independent analyses** - Gurus don't debate, each forms own thesis
2. **All preserved** - Consolidation adds, never removes
3. **Expert-driven data** - Each guru specifies needs, orchestrator fetches union
4. **Visible DRIVER** - Show stage markers as skill runs
5. **Always ask** - Quick vs Full mode selection each time
6. **Changes > Holdings** - For 13-F, recent changes more important than static positions
7. **Bold forward-looking** - Internal use, no hedging, specific predictions

## File Structure Target

```
financial-researcher/
├── SKILL.md                      # Main orchestrator
├── experts/
│   ├── _template.md              # Base template all experts extend
│   ├── warren_buffett.md
│   ├── ben_graham.md
│   ├── peter_lynch.md
│   ├── cathie_wood.md
│   ├── george_soros.md
│   ├── ray_dalio.md
│   └── michael_burry.md
├── references/
│   └── DRIVER_Best_Practices.md  # Copy from DRIVER folder
├── mcp/
│   ├── financialdatasets-mcp/
│   │   ├── pyproject.toml
│   │   ├── README.md
│   │   └── src/
│   │       ├── __init__.py
│   │       └── server.py
│   └── tavily-mcp/
│       ├── pyproject.toml
│       ├── README.md
│       └── src/
│           ├── __init__.py
│           └── server.py
├── templates/
│   ├── expert_output_schema.json
│   └── consolidated_report_template.md
└── .env.example
```

## Completion Signals

Output the appropriate promise tag when done:

- Round complete but phase continues: Just update checkbox, continue
- Phase 1 complete: `<promise>PHASE 1 COMPLETE</promise>`
- Phase 2 complete: `<promise>PHASE 2 COMPLETE</promise>`
- Phase 3 complete: `<promise>PHASE 3 COMPLETE</promise>`
- Phase 4 complete: `<promise>PHASE 4 COMPLETE</promise>`
- Phase 5 (MVP) complete: `<promise>MVP COMPLETE</promise>`

## Iteration Protocol

```
1. Read RALPH_EXECUTION_PLAN.md
2. Find current round (first unchecked)
3. Read any existing files in financial-researcher/
4. Execute round requirements completely
5. Update checkbox in RALPH_EXECUTION_PLAN.md
6. If phase done → output promise
7. If phase continues → proceed to next round
```

## Remember

- You see your previous work in the files
- Build incrementally on what exists
- Quality over speed
- No placeholders - complete each piece fully
- When in doubt, refer to design docs
- This is for internal use - be bold and specific in predictions
