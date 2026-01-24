# Financial Researcher

7 legendary investors analyze any stock. One command.

```
/financial-researcher AAPL
```

## What It Does

Fetches financial data, runs it through Python metrics calculators, then dispatches 7 AI analysts in parallel:

| Investor | Focus |
|----------|-------|
| Warren Buffett | Moats, owner earnings |
| Ben Graham | Margin of safety |
| Peter Lynch | PEG, growth story |
| Cathie Wood | Disruption, TAM |
| George Soros | Reflexivity |
| Ray Dalio | Cycles, stress tests |
| Michael Burry | Forensics, bear case |

Returns: Signal consensus, price targets, risk matrix, full report.

## Setup

Requires [Claude Code](https://claude.ai/claude-code) with MCP servers:

```
financialdatasets-mcp  # Financial data
tavily-mcp             # News/search
```

## Output

- Markdown report to console
- JSON + MD saved to `reports/`

## Structure

```
financial-researcher/
├── skills/financial-researcher/   # Skill definition
├── processing/                    # Python metrics (Piotroski, Altman, etc.)
└── reports/                       # Generated analyses
```

## License

MIT
