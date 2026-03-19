# KWIZERANA DeFi Tools

Professional DeFi scanning and grid accumulation tools. Fully self-contained — no build step, no backend, no API keys required.

## Tools

### 📊 KWIZERANA DexScreener (`KWIZERANA.html`)
Multi-chain DeFi scanner with KWI scoring system.
- 7 chains: Avalanche, Base, Solana, Ethereum, BNB, Bittensor, Aptos
- KWI Score (RSI + MACD + Volume + Trend)
- TradingView-style candlestick charts (lightweight-charts, fully inlined)
- Sortable pair tables, filter pills, live price simulation

### 🤖 Grid Bot Dashboard (`GRID_BOT.html`)
Advanced grid accumulation bot for PHAR (AVAX) and AERO (Base).
- Grid types: Arithmetic, Geometric, Fibonacci
- Trailing Up + Expansion Down adaptive features
- Backtest tab with equity curve, Sharpe ratio, max drawdown, win rate
- MetaMask wallet connection (reads balances on AVAX + Base)
- Volatility-based grid spacing recommendations (ATR)

## Deployment

### GitHub Pages (Recommended)
1. Fork or clone this repo
2. Go to **Settings → Pages → Source → main branch / root**
3. Your site is live at `https://yourusername.github.io/repo-name`

MetaMask works automatically on HTTPS (GitHub Pages provides this).

### Local (with MetaMask)
```bash
python3 -m http.server 8765
# Open http://localhost:8765
```

### Local (no MetaMask needed)
Just double-click `KWIZERANA.html` or `GRID_BOT.html` — everything works from `file://` except MetaMask.

## Real Backtest Data

To use real historical price data instead of simulation:
```bash
pip3 install requests
python3 FETCH_DATA.py
```
This fetches 90 days of OHLCV from GeckoTerminal/CoinGecko and saves `price_data.json`. The Grid Bot detects this file automatically and uses real prices in backtests.

## Strategy (Default Config)

| Token | Chain | Budget | Levels | Range |
|-------|-------|--------|--------|-------|
| PHAR  | Avalanche | $1,500 | 8 | $131–$180 |
| AERO  | Base | $2,000 | 10 | $0.110–$0.310 |

**Why AERO?** Trading at $0.34 vs ATH of $2.32 (–85%). Q2 2026 Aero unified platform launch catalyst.

## Disclaimer
These tools are for informational and educational purposes only. They do not execute trades. Not financial advice. DeFi involves significant risk of loss.

## License
MIT
