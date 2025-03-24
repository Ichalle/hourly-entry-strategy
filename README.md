# Time-Based Trading Strategy with TP/SL

![Strategy Visualization](https://i.imgur.com/gadWnpK.png) 

## Strategy Overview
This Pine Script implements a time-based trading strategy that:
- Enters long positions at a specific hour each day
- Uses fixed percentage-based take profit and stop loss levels
- Allows backtesting over a customizable period

## Features
- 🕒 **Time-based entries** at user-defined hour
- ⚖️ **Risk management** with adjustable TP/SL
- 📊 **Visual indicators** on chart
- 📝 **Summary table** with key parameters
- ⏱️ **Customizable backtest period**

## Input Parameters
| Parameter | Description | Default | Range |
|-----------|-------------|---------|-------|
| `Entry Hour` | Hour for trade entries (24h format UTC+0 Time) | 1 | 0-23 |
| `Backtest Period` | Number of days to test | 30 | ≥1 |
| `Take Profit` | Profit target percentage | 2.0% | 0.1-100% |
| `Stop Loss` | Risk limit percentage | 1.5% | 0.1-100% |

## How It Works
1. **Entry Condition**:
   - Triggers at the specified hour (e.g., 01:00)
   - Only enters if no position is currently open

2. **Exit Conditions**:
   - Take Profit: Closes at `entry_price × (1 + TP%)`
   - Stop Loss: Closes at `entry_price × (1 - SL%)`

3. **Visualization**:
   - ▲ Green triangle: Entry points
   - Green dashed line: Take Profit level
   - Red dashed line: Stop Loss level

## Installation
1. Open TradingView chart
2. Click "Pine Editor" tab
3. Paste the entire script
4. Click "Add to Chart"

## Customization Tips
- Adjust `Entry Hour` to test different trading sessions
- Modify TP/SL ratios to match your risk appetite
- Increase `Backtest Period` for more robust results
- Combine with other indicators by adding filters to entry condition

## Example Use Cases
- Comparing different TP/SL ratios (e.g., 1:1 vs 2:1 risk-reward)
- Analyzing specific market hours' profitability

## Backtest Results Interpretation
Check the Strategy Tester tab for:
- ✔️ Win rate percentage
- 💰 Profit factor
- 📈 Sharpe ratio
- 🔄 Number of trades

## Limitations
- Only tests long positions
- Uses fixed percentage-based exits
- Doesn't account for slippage/spreads
- Minute-based precision depends on chart timeframe

> **Note**: Always forward test strategies before live trading. Past performance doesn't guarantee future results.