**India's Equity Market Rank Decline: Structural or Macro?** | *Python, pandas, statsmodels, MSCI/NSDL data* | Jun 2026

## Research Question

Is India's loss of equity market rank a temporary macro shock (rupee depreciation, FII outflows,
valuation reset) or a structural story (no AI/semiconductor exposure in index composition)?
And how much of the capital outflow was forced by passive index mechanics vs. active investor decisions?

## Background

India is the world's 6th largest economy by GDP. South Korea ranks 13th, Taiwan 21st.
Yet in May 2026, both overtook India in equity market capitalisation — a gap that was
3.5x in India's favour just 18 months earlier.

## Hypotheses Tested

- **H1 (Lead-Lag):** Do MSCI EM weight changes precede FII outflows, or the reverse?
- **H2 (Passive Flow):** How much of India's FII outflow is mechanically explained by MSCI weight reduction vs. active decisions?
- **H3 (Structural Decomposition):** Is India's underperformance vs Korea/Taiwan explained by currency and valuation (reversible) — or by sector composition (structural)?

## Findings

**H1/H2 — Passive vs Active Flows**
Of India's **$41.6B FII outflow** (Jan 2025–May 2026):
- **66% passive/mechanical** — forced by MSCI EM weight reduction (India: 20% → 11%), using $300B estimated passive AUM tracking the index
- **34% active/discretionary**

A Granger causality test was run to test lead-lag direction, but the result (p=0.0148, lag 3)
does not survive multiple-comparison correction on non-stationary series — flagged as
exploratory only. The passive/active split above is the robust finding for H1/H2.

**H3 — Structural vs Macro**
Decomposed India's **-254.3pp USD return gap vs South Korea**:
- Currency (INR depreciation): **-9.7pp** → reversible
- Valuation re-rating (P/E): **-3.7pp** → partially reversible
- Sector composition (structural): **-240.8pp** → **95% of total gap**

**BHB Sector Attribution** (refined IT split — Services / Semiconductors / AI Foundry):
- India: 0% semiconductors, 0% AI foundry vs Korea: 37% semiconductors, 2% AI foundry
- Combined IT structural drag: **-30.3pp**
- Remaining gap: India's IT services sector (-42.4%) underperformed while Korea's
  semiconductor sector (+72.4%) rode the AI rally — same structural root cause,
  different sub-sector exposure

## Conclusion

Even full INR recovery and P/E normalisation would close only ~5% of the gap.
The remaining ~95% persists until Indian companies appear in the global
semiconductor/AI supply chain with meaningful index weight.

**Note:** The -254.3pp gap reflects a snapshot during an extreme AI-driven rally
(Korea's KOSPI hit an all-time high in May 2026). The exact magnitude will vary —
the durable finding is the *direction and dominance of the structural component*.

## Methodology

1. Data collection — MSCI EM/country factsheets, NSDL FPI flows, NSE P/E, Yahoo Finance prices/FX
2. Passive flow estimation (MSCI weight change × passive AUM proxy)
3. Granger causality test (weight changes vs FII flows)
4. Currency & valuation decomposition (USD return = local return × FX return)
5. Brinson-Hood-Beebower sector attribution with refined IT sub-categories

## Limitations

- MSCI weights and FII flows are approximate/interpolated where exact monthly data wasn't available
- Passive AUM estimate ($300B) is a conservative lower bound; institutional mandates may push this to $400-500B
- Sector returns use single-stock proxies (e.g., Infosys for IT Services) rather than full sector indices