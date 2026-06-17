# Learning Record 0006 — 13F & Institutional Holdings

**Date**: 2026-06-17
**Lesson**: 0006-13f-institutional-holdings.html
**Status**: Completed

## Key insights

1. **The nature of 13F**: a snapshot at quarter end, not a quarterly flow statement. All period-over-period comparisons are "approximate rebalancing" between two adjacent 13F filings -- not real turnover.
2. **Unit trap is a bug high-risk zone**: `value_x1000` field name = "in thousands of dollars." Misplacing by 1000x is a classic error. Verification method: stock price × shares ≈ value_x1000 × 1000.
3. **Period-over-period comparison: look at share count, not market value** -- share count changes = active rebalancing; market value changes are polluted by stock price fluctuations. If an institution holds 1M CVNA shares unchanged and the stock goes from $100 to $150, that is passive market value appreciation, not an addition.
4. **13F blind spots are structural constraints**: covers only long positions, only U.S. stocks, only quarter-end, only institutions >$100M AUM. It cannot capture shorts, options, intra-quarter adjustments, small institutions, or retail investors. **This means 13F can answer "who is buying and selling," but not "why they are buying and selling."**
5. **Boundary conditions (5 position states)**: Initiation / Liquidation / Increase / Decrease / No change. Use FULL OUTER JOIN and fill with institution_name to avoid division by zero when prev_value = 0.
6. **Aggregate rankings by institution, not simple SUM**: Carvana's $1.92B position vs UXIN's $3M position differs by 600x -- direct summation would drown UXIN's signal. Top Buyers/Sellers must be grouped "per ticker" or "per institution."
7. **IHS Markit report pages P2-P7 are built almost entirely on 13F data** -- this is why 13F is called the "data foundation of cross-holding analysis."

## Action items

- Verify: check whether cross_holding.py's pivot_table is grouped and sorted "per ticker" (not simple SUM)
- Verify: check whether the value_x1000 field is kept in SEC raw units throughout the data pipeline
- Follow-up: consider adding a "share count change vs market value change" comparison card to the Dashboard for more accurate Top Buyers/Sellers rankings
