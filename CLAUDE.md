# Financial Researcher

## Structure

```
financial-researcher/
├── skills/financial-researcher/SKILL.md   # Orchestration logic
├── processing/                            # Python metrics
└── reports/                               # Output
```

## Rules

- SKILL.md controls orchestration. Read fully before editing.
- Python layer calculates metrics. Claude does analysis.
- Test: `python -m processing.test_pipeline`

## Key Files

- `processing/metrics_calculator.py` - Piotroski, Altman, Beneish, etc.
- `processing/orchestrator.py` - `run_analysis()` entry point
