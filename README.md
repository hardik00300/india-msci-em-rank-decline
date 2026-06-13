**India's Equity Market Rank Decline: Structural or Macro?** | *Python, pandas, statsmodels, MSCI/NSDL data* | Jun 2026

- Decomposed India's **$41.6B FII outflow** (Jan 2025–May 2026) into **passive/mechanical (66%)** vs **active/discretionary (34%)** flows, using MSCI EM weight changes × $300B estimated passive AUM tracking the index.
- Decomposed India's **-254.3pp USD return gap vs South Korea** into currency (-9.7pp, reversible), valuation re-rating (-3.7pp, partially reversible), and structural sector composition (-240.8pp) — **structural component = 95% of the total gap.**
- **BHB sector attribution** with a refined IT split (Services / Semiconductors / AI Foundry) shows India's zero exposure to semiconductors (0% vs Korea's 37%) and AI foundry (0% vs Korea's 2%) is the dominant driver — combined IT structural drag of -30.3pp, with the remaining gap explained by India's IT sector (-42.4%) underperforming while Korea's semiconductor sector (+72.4%) rode the AI rally.
- Granger causality on weight changes vs FII flows was run but does not survive multiple-comparison correction (non-stationary series, p=0.0148 at lag 3 only) — flagged as exploratory, not a headline finding.

**Note:** The -254.3pp gap reflects a specific snapshot during an extreme AI-driven rally (Korea's KOSPI hit an all-time high in May 2026). The exact magnitude will vary month to month — the durable finding is the *direction and dominance of the structural component*, not the precise figure.

## Methodology
1. Passive flow estimation (MSCI EM weight × passive AUM proxy)
2. Granger causality test (weight changes vs FII flows)
3. Currency & valuation decomposition (USD return = local return × FX return)
4. Brinson-Hood-Beebower sector attribution with refined IT sub-categories

## Data Sources
- MSCI EM/India/Korea/Taiwan factsheets (msci.com)
- NSDL FPI flow data (fpi.nsdl.co.in)
- NSE historical P/E data
- Yahoo Finance (index levels, FX rates)

## Limitations
- MSCI weights and FII flows are approximate/interpolated where exact monthly data wasn't available
- Passive AUM estimate ($300B) is a conservative lower bound; institutional mandates may push this to $400-500B
- Sector returns use single-stock proxies (e.g., Infosys for IT Services) rather than full sector indices