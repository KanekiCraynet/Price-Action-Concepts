# Price Action Concepts Open Source 🎴 - TradingView Indicator Documentation

## Overview
**Price Action Concepts Open Source 🎴** is a comprehensive TradingView indicator designed to identify key market structure elements, liquidity zones, and price action patterns. It combines multiple concepts from institutional trading strategies, including Break of Structure (BOS), Change of Character (CHoCH), Order Blocks, and Fair Value Gaps. This open-source tool is ideal for traders analyzing forex, crypto, and equities markets.

![Example Chart](https://via.placeholder.com/800x400?text=Price+Action+Concepts+Example)  
*Example: Market structure with BOS/CHoCH signals and liquidity zones*

---

## Key Features
1. **Market Structure Analysis**
   - Swing Structure (BOS/CHoCH)
   - Internal Market Structure
   - Strong/Weak High/Low Points

2. **Liquidity Concepts**
   - Liquidity Sweeps Detection
   - Trendline Liquidity Zones

3. **Order Block Analysis**
   - Volumetric Order Blocks (Multi-Timeframe)
   - Order Block Mitigation Detection

4. **Advanced Tools**
   - Fair Value Gaps (FVG)
   - Equal Highs/Lows
   - Premium/Discount Zones

5. **Multi-Timeframe Analysis**
   - Built-in Structure Scanner
   - 3 Customizable Timeframe Inputs

---

## Installation
1. **Copy Code**:  
   Save the provided Pine Script code as `Price_Action_Concepts_Open_Source.tv`
   
2. **Add to TradingView**:  
   `Open TradingView → Pine Editor → Paste Code → Add to Chart`

---

## Configuration Guide

### 1. Core Settings
| Parameter | Description | Options/Values |
|-----------|-------------|----------------|
| `Market Concepts Mode` | Display historical or current structure | Historical/Present |
| `Color Candles` | Color-code candles based on trend | On/Off |
| `Style` | Visual theme | Colored/Monochrome |

### 2. Market Structure
![Structure Example](https://via.placeholder.com/600x300?text=BOS+CHoCH+Example)

#### Internal Structure
```pine
input bool   SHOW_INTERNAL = true
input string STRUCTURE_TYPE = "All"  // [BOS, CHoCH]
input color  BULL_COLOR    = #089981
input color  BEAR_COLOR    = #f23645
```

#### Swing Structure
```pine
input int    SWING_LENGTH  = 50
input string SWING_STYLE   = "Dashed"
```

### 3. Liquidity Analysis
```pine
// Liquidity Sweeps
input bool   LIQUIDITY_SWEEPS  = true
input int    SWEEP_LENGTH      = 3
input color  BULLISH_SWEEP_COL = #0044ff
input color  BEARISH_SWEEP_COL = #ff2b00

// Trendline Liquidity
input bool   AUTO_TRENDLINES   = true
input int    TRENDLINE_SENS    = 3
```

### 4. Order Blocks
```pine
input int    ZONE_COUNT        = 5
input string MITIGATION_METHOD = "Wick"  // [Wick, Close]
input color  BULL_OB_COLOR     = #22a08a
input color  BEAR_OB_COLOR     = #f23847
```

### 5. Advanced Features
```pine
// Fair Value Gaps
input bool   SHOW_FVG         = true
input string FVG_TIMEFRAME    = "Current"

// Equal Highs/Lows
input bool   SHOW_EQHL        = false
input int    EQHL_CONFIRM_BARS= 3
```

---

## Alert Conditions
| Alert Type | Trigger Condition | Use Case |
|------------|-------------------|----------|
| `Bullish BOS` | Price breaks swing high with momentum | Trend confirmation |
| `Bearish CHoCH` | Failed break of structure | Potential reversal |
| `Liquidity Sweep` | Wick exceeds recent swing | Stop hunt detection |
| `Order Block Break` | Price closes beyond OB boundary | Institutional level break |

---

## Best Practices
1. **Multi-Timeframe Confirmation**  
   Use the built-in scanner with:
   ```pine
   input.timeframe SCANNER_TF = "D"
   ```
   
2. **Order Block Trading**  
   - Look for OB coinciding with premium/discount zones
   - Combine with FVG for high-probability entries

3. **Structure Analysis**  
   ```mermaid
   graph LR
   A[Internal BOS] --> B[Swing CHoCH]
   B --> C[New Trend Confirmation]
   ```

---

## Open Source Notes
**License:** MIT License  
**Contribution:**  
```bash
git clone https://github.com/KanekiCraynet/Price-Action-Concepts.git
```
**Dependencies:**  
- TradingView v5.0+
- No external libraries required

---

## Disclaimer
This indicator is provided "as-is" for educational purposes only. Trading involves substantial risk - always test strategies in a demo account first. The developers assume no liability for financial losses incurred using this tool.
