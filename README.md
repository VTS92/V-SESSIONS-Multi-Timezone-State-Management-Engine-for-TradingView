# V-Sessions Engine — Multi-Timezone Session Mapping with POC, LVN & VWAP

**Pine Script v5 | TradingView | Institutional Session Analysis**

Built and used daily in live trading. Part of the V-Suite — works best combined with the [V-WAPE Engine](https://github.com/VTS92/V-WAPE-Engine) and the [V-Profile Matrix](https://github.com/VTS92/V-Profile-HD).

---

## What it does

V-Sessions maps where, when, and how the major global trading sessions interact with price. It answers one question: **how is each session distributing volume — and where are the imbalances?**

The indicator combines four layers, all anchored to each individual session:

**Multi-Timezone Session Mapping**
- London (RTH + Electronic), New York (RTH + Electronic), Tokyo, Sydney — each rendered as a dedicated session box with persistent high/low tracking
- DST auto-handled via native timezones (Europe/London, America/New_York, Asia/Tokyo, Australia/Sydney)
- UDT-based state engine with 500-object optimization for clean charts on long histories

**Per-Session Point of Control (POC)**
- Highest-volume price level computed *within each session* using lower-timeframe volume aggregation
- Updated dynamically as the session progresses; locked at session close
- Identifies where institutional activity concentrated during each market window

**Per-Session Low Volume Nodes (LVN) with Mitigation**
- Detects intra-session price levels where volume traded far below the session average — areas price tends to move through quickly
- LVNs persist after the session closes and remain on the chart until price retests them
- Built-in mitigation logic: LVN boxes are removed (or trimmed) on the first touch, leaving only unmitigated imbalances

**Anchored VWAP & Standard Deviation Bands**
- VWAP anchored by Session, Week, Month, Quarter, Year, Decade or Century
- 3 levels of deviation bands (Standard Deviation or Percentage mode)
- Master toggles for POC / LVN / VWAP / BANDS for clean chart composition

---

## Screenshots

![V-Sessions Overview](v-sessions-multi-timezone-market-mapping-engine.png)
![V-Sessions Detail](v-sessions-institutional-liquidity-state-management.png)

---

## How to use

1. Open TradingView and go to **Pine Editor**
2. Paste the contents of `V-Sessions-Engine.pine`
3. Click **Add to chart**
4. Activate the sessions you want under **"SESSIONS ACTIVATION"** (London RTH/ETH, New York RTH/ETH, Tokyo, Sydney)
5. Toggle the four global layers under **"GLOBAL CONFIGURATIONS"**: POC · LVN · VWAP · BANDS
6. Set your **VWAP Anchor Period** (Session for intraday, Week/Month for swing)

---

## Configuration

| Parameter | Default | Description |
|---|---|---|
| Sessions activation | NY (RTH + ETH) | Toggle each session independently |
| POC | On | Per-session Point of Control line |
| LVN | On | Per-session Low Volume Node detection with mitigation |
| VWAP | On | Anchored VWAP line |
| Bands | On | 3 deviation bands around VWAP |
| Anchor Period | Session | VWAP reset window (Session → Century) |
| Bands Calculation Mode | Standard Deviation | Std Dev or Percentage |
| Band Multipliers | 1.0 / 2.0 / 3.0 | Three configurable bands |
| Hist (per session) | varies | Keep historical sessions visible on chart |

---

## Part of the V-Suite

V-Sessions works best when combined with the rest of the suite:
- **[V-Profile Matrix](https://github.com/VTS92/V-Profile-HD)** — full volume profile (POC, Value Area, HVN/LVN) on configurable anchor periods
- **[V-WAPE Engine](https://github.com/VTS92/V-WAPE-Engine)** — anchored VWAP with volume shock detection and live volatility dashboard

**How they fit together:** V-Sessions tells you *when* each market is active and how it's distributing volume. V-Profile Matrix tells you *where* volume concentrated on the bigger timeframe. V-WAPE tells you *whether price is overextended* from fair value right now.

---

## Author

**Vito Santarsiero** — Trading Platform Operations Specialist | CISI IOC Candidate | London, UK

[LinkedIn](https://linkedin.com/in/vito-santarsiero) · [V-WAPE Engine](https://github.com/VTS92/V-WAPE-Engine) · [V-Profile Matrix](https://github.com/VTS92/V-Profile-HD)

