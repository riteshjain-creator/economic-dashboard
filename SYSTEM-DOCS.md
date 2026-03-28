# Economic Dashboard - System Documentation

**Deployed:** March 28, 2026  
**URL:** https://riteshjain-creator.github.io/economic-dashboard/  
**GitHub:** https://github.com/riteshjain-creator/economic-dashboard

---

## Overview

A **narrative-first economic intelligence dashboard** designed for daily market synthesis. Philosophy: **Signal over noise.**

---

## Design Principles

1. **Commentary-first** → Narrative drives the page, data supports
2. **Signal over noise** → Curated sources only (vetted analysts)
3. **Desktop-first** → Information density optimized
4. **Sidebar navigation** → Jump to any section, access history
5. **Real charts** → Plotly (professional, interactive)
6. **Transparent sourcing** → Links to all sources used

---

## Architecture

### **Frontend**
- **HTML/CSS/JavaScript** (static site)
- **Plotly.js** for charts (interactive, professional)
- **GitHub Pages** hosting (free, fast, global CDN)

### **Backend (Automation)**
- **OpenClaw cron jobs** (twice daily)
- **Data collection** from NSE, Yahoo Finance, Bloomberg
- **AI synthesis** (Claude Sonnet 4.5 via OpenClaw)
- **Git version control** (every update is a commit)

### **Update Schedule**
- **8:30 AM IST:** Pre-market brief (global overnight, futures, news)
- **4:30 PM IST:** Post-market full synthesis (close, analysis, sources)

---

## Dashboard Sections

### **1. Synopsis**
- Today's headline + subheadline
- Narrative summary (what happened, why it matters)
- Key Takeaway box (TL;DR)
- Market Regime assessment (VIX, PCR, breadth, FII flows)
- Charts embedded in narrative

### **2. Market Structure**
- Breadth indicators (Advance/Decline, 52W High/Low)
- Market cap analysis (Large/Mid/Small cap rotation)
- Volume/liquidity trends

### **3. Sector Rotation**
- Which sectors led/lagged
- Flight to safety vs risk-on behavior
- Heatmap visualization
- Historical context (last time this happened...)

### **4. Macro Forces**
- Oil, gold, USD/INR
- FII/DII flows
- Global market context (US, Asia)
- Interest rates, yields
- Geopolitical events

### **5. Technical Snapshot**
- Key support/resistance levels
- RSI, moving averages
- Swing highs/lows, unfilled gaps
- Trend analysis

### **6. Sources & Context** ✨ NEW
- News articles (2)
- Analyst commentary (1-2)
- Institutional research (1)
- Data sources list

**Purpose:** Transparency + learning. Show where insights came from.

### **7. Trading Playbook**
- What to do tomorrow
- Scenario planning (if market gaps up/down/flat)
- Sectors to watch
- Risk management

---

## Sidebar Navigation

### **TODAY**
- Synopsis
- Market Structure
- Sector Rotation
- Macro Forces
- Technical Snapshot
- Sources & Context
- Trading Playbook

### **PAST DAYS**
- Mar 27, 26, 25, 24, 23...
- (Click to access archived analysis)

### **ARCHIVE**
- This Week
- Last Week
- This Month

---

## Data Sources

### **Market Data**
- NSE India (Nifty, Sensex, sector indices)
- Yahoo Finance (historical data)
- NSDL (FII/DII flows)

### **News & Commentary**
**Tier 1 (Use these):**
- Analysts: Neelkanth Mishra, Sajjid Chinoy, Raghuram Rajan, Arvind Subramanian
- Publications: Mint, Economic Times, Indian Express, Business Standard
- Institutional: RBI Bulletins, Economic Survey, IMF/World Bank reports

**Tier 2 (Verify before using):**
- Bank economists (HDFC, Nomura, HSBC)
- Bloomberg Quint, Reuters India

**Avoid:**
- Zee Business, finfluencers, unvetted sources

---

## Cron Jobs

### **Morning Update (8:30 AM IST)**
**Cron:** `0 3 * * *` (Asia/Kolkata)  
**Session:** Isolated  
**Timeout:** 900 seconds (15 min)

**Tasks:**
1. Fetch global overnight data (US, Europe, Asia)
2. Check Nifty/Sensex futures
3. Scan 3-5 news stories (Tier 1 sources only)
4. Generate brief synthesis
5. Update index.html
6. Post to Discord
7. Git commit + push

### **Evening Update (4:30 PM IST)**
**Cron:** `0 11 * * *` (Asia/Kolkata)  
**Session:** Isolated  
**Timeout:** 1200 seconds (20 min)

**Tasks:**
1. Fetch market close data (Nifty, sectors, commodities, sentiment)
2. Research credible sources (podcasts, articles, reports)
3. Generate full synthesis (all sections)
4. Create 3-4 Plotly charts
5. Update index.html
6. Post to Discord
7. Archive to synthesis/YYYY-MM-DD.md
8. Git commit + push

---

## File Structure

```
economic-dashboard/
├── index.html              # Main dashboard (production)
├── README.md               # Project overview
├── sources.md              # Vetted sources list
├── data/
│   ├── YYYY-MM-DD.json     # Daily data snapshots
│   └── history.json        # Aggregated historical data
├── synthesis/
│   └── YYYY-MM-DD.md       # Archived daily synthesis
├── learning/
│   └── priorities.md       # Auto-updated based on feedback
└── scripts/
    └── update-dashboard.sh # Update script (called by cron)
```

---

## Learning System

**How it improves over time:**

1. **Discord feedback loop**
   - User questions → note topics of interest
   - "Why did pharma spike?" → track pharma more closely
   - "Who is this analyst?" → vet sources better

2. **Pattern recognition**
   - Track which news actually moved markets
   - Which sources were right vs wrong
   - Which correlations hold (oil up → airlines down)

3. **Priority tracking**
   - Update learning/priorities.md based on usage
   - Focus on sectors/stocks user cares about

---

## Key Indicators Tracked

### **Daily (Must Track)**
1. Nifty 50, Midcap, Smallcap (breadth check)
2. Advance/Decline Ratio
3. India VIX / Market Mood Index
4. Nifty PCR (Put/Call Ratio)
5. USD/INR
6. Brent Crude Oil
7. FII/DII flows
8. Top 3 sectoral movers
9. Key news events

### **Weekly Review**
1. RSI levels (Nifty + sectors)
2. Swing highs/lows, unfilled gaps
3. Open Interest changes
4. 50 DMA / 200 DMA positioning
5. Sector rotation trends

### **Monthly Context**
1. 52-week high/low count trend
2. RBI policy stance / yield curve
3. Historical pattern comparison

---

## Critical Constraints

### **Signal vs Noise**
- **Include:** Only sources that informed today's synthesis
- **Exclude:** Generic wrap-ups, finfluencers, repeated info
- **Result:** 3-6 sources per day (not 20)

### **Commentary First**
- Text is PRIMARY (large, readable)
- Charts are SECONDARY (embedded as evidence)
- Data in context boxes (supporting role)

### **Curated Sources**
- Use Tier 1 analysts only (from sources.md)
- Verify track record before citing
- Attribute properly (transparency)

---

## Usage Workflow

### **For User (Ritesh)**
1. Open dashboard daily (morning + evening)
2. Read synopsis (10-second summary)
3. Explore sections via sidebar (click to jump)
4. Check sources (go deeper if needed)
5. Discuss on Discord (share insights)
6. Give feedback (what to track more/less)

### **For System (Fidato)**
1. Wake up on cron (8:30 AM / 4:30 PM IST)
2. Fetch data from APIs
3. Research credible sources
4. Generate synthesis (AI-powered)
5. Update dashboard HTML
6. Post to Discord
7. Archive synthesis
8. Git commit + push
9. Learn from feedback

---

## Maintenance

### **Daily**
- Cron jobs run automatically
- No manual intervention needed

### **Weekly**
- Review learning/priorities.md
- Check if sources are still credible
- Adjust indicators based on feedback

### **Monthly**
- Audit sources.md (add/remove analysts)
- Review historical synthesis quality
- Refine signal/noise ratio

---

## Future Enhancements

**Phase 2 (Next Month):**
- Make sidebar navigation functional (click to load sections)
- Add week/month archive views
- Implement pattern recognition (regime detection)
- Add stock-level tracking (user-selected watchlist)

**Phase 3 (Month 3):**
- Predictive patterns ("Last 3 times oil hit $100...")
- Proactive alerts ("Oil just broke $110 — airlines will get hit")
- Custom dashboards (sector-specific, technical-focused, macro-focused)

---

## Contact & Feedback

**Discord:** #daily-economic-update channel  
**GitHub Issues:** https://github.com/riteshjain-creator/economic-dashboard/issues

---

**Built:** March 28, 2026  
**Philosophy:** Signal Over Noise  
**Mission:** Turn market noise into actionable intelligence
