# Tauric Tyche Project

**Multi-Agent LQ45 Stock Analysis for Indonesia Market**

## Overview

Tauric Tyche is an automated stock analysis system that uses a multi-agent AI pipeline (powered by Qwen2.5:7b on NVIDIA Tesla P4 GPU) to analyze all LQ45 Indonesian stocks weekly.

## Methodology

- **Model:** Qwen2.5:7b-instruct-Q4_K_M (local GPU inference)
- **Stack:** TradingAgents multi-agent framework + yfinance + Ollama
- **Agents:** Market analyst, news analyst, fundamental analyst, risk manager
- **Coverage:** 45 LQ45 stocks across 10 sectors

## Output Structure

```
week_YYYY-WW/            # Weekly batch
├── BBCA.md              # Per-stock analysis (markdown)
├── BBRI.md
├── ...
├── COMPARISON.md        # Cross-stock ranking table
├── SECTOR_SUMMARY.md    # Sector-level heatmap
├── charts/              # Price charts (PNG)
└── reports.pdf          # Full PDF report

live_YYYY-MM-DD_HHMM/    # Live/on-demand analysis
├── BBCA.md
├── ...
├── COMPARISON.md
├── lq45_table.csv       # Raw data table
└── raw.json             # Full raw data
```

## Access

- **Web Dashboard:** http://10.10.10.11:8080/
- **Blog:** https://kangifaz.com/docs/tauric-tyche/
- **Reports:** Weekly PDF + ZIP download

## Usage

```bash
# Run live analysis
source venv/bin/activate
python3 tauric_live.py

# Generate PDF
python3 tauric_pdf.py

# Start web server
python3 tauric_web.py 8080
```

## License

MIT — Kang Ifaz