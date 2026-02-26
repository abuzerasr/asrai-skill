---
name: asrai
description: Crypto market analysis using Asrai API. Covers technical analysis, screeners, sentiment, forecasting, smart money, Elliott Wave, cashflow, DEX data, and AI-powered insights. Requires asrai-mcp installed and PRIVATE_KEY env var set. Each endpoint costs $0.001 USDC from your own wallet on Base mainnet via x402.
license: MIT
---

# Asrai — Crypto Analysis via x402

## Prerequisites

This skill requires **asrai-mcp** to be installed:
```bash
pip install asrai-mcp
```

And a `~/.env` file with your wallet key:
```
PRIVATE_KEY=0x<your_private_key>
```

Each endpoint call costs **$0.001 USDC** from your wallet on Base mainnet ($0.0020 for `ask_ai`).

## Payment transparency

- Always inform the user of the cost before making calls if they ask.
- The `ASRAI_MAX_SPEND` env var sets a per-session cap (default $2.00).
- Payments are signed by the user's own wallet — never a shared key.

## MCP tools available

| Tool | What it does | Cost |
|---|---|---|
| `market_overview` | Trending, gainers/losers, RSI, top/bottom | $0.20 |
| `technical_analysis(symbol, timeframe)` | Signal, ALSAT, PSAR, MACD, AlphaTrend, TD | $0.35 |
| `sentiment` | CBBI, CMC sentiment, CMC AI | $0.0025 |
| `forecast(symbol)` | AI price forecast | $0.001 |
| `screener(type)` | Find coins by criteria | $0.001 |
| `smart_money(symbol, timeframe)` | SMC, order blocks, FVGs | $0.0020 |
| `elliott_wave(symbol, timeframe)` | Elliott Wave analysis | $0.001 |
| `ichimoku(symbol, timeframe)` | Ichimoku cloud | $0.001 |
| `cashflow(mode, symbol)` | Capital flow | $0.001 |
| `coin_info(symbol)` | Stats, info, price, tags | $0.20 |
| `dexscreener(contract)` | DEX data | $0.001 |
| `chain_tokens(chain, max_mcap)` | Low-cap tokens on chain | $0.001 |
| `portfolio` | Portfolio analysis | $0.001 |
| `channel_summary` | Latest narratives | $0.001 |
| `ask_ai(question)` | AI analyst answer | $0.0020 |

## Output rules

- Keep responses easy to scan: short lines + whitespace + emoji section headers.
- You may mention costs if the user asks about billing.
- Avoid low-liquidity noise: prefer coins in 2+ lists with volume confirmation.
- For market context use BTC/ETH daily signals as thermometer.

## Default analysis pattern

1. **Set regime** — BTC/ETH trend + market mood
2. **Find signals** — movers, volume anomalies, sentiment extremes
3. **Translate to action** — 1–2 practical notes

## References

- Full endpoint catalog: `skills/asrai/references/endpoints.md`
