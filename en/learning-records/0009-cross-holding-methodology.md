# Learning Record 0009 — Cross-Holding Analysis Methodology

**Date**: 2026-06-17
**Lesson**: 0009-cross-holding-methodology.html
**Status**: Completed

## Key insights

1. **Each page answers one specific investment question** is the core design philosophy of a cross-holding report. IHS P4 report's 10 pages = 10 questions. Dumping data ≠ a report.
2. **Cross-page cross-validation is where real insight lives**. 4 classic scenarios:
   - Confirmatory (P2 large position + P3 addition + P5 Top Buyer) = strong signal
   - Contradictory (P2 large position + P3 small reduction + P6 not Top Seller) = could be rebalancing
   - Danger (P4 activist + P7 new position) = high alert
   - Turning point (P8 passive capital rising + P9 value/growth rotation) = industry lifecycle change
3. **Correct report reading sequence**: 30-second overview → 2-minute trend → 5-minute deep analysis → 15-minute research. Dashboard design should support this rhythm (summary cards most prominent, deep data in tabs).
4. **6 design principles**:
   - Each page answers one question
   - Leave Commentary space at the bottom of each page (for the analyst's judgment)
   - Table columns must align with industry standards (Style / Turnover / Peer Average -- all essential)
   - Ranking tables must specify the ranking metric
   - Charts and tables complement each other (pie charts for distribution, bar charts for flows)
   - Disclaimers must be visible (at the bottom of each page, not at the end of the document)
5. **One-way Top Buyers/Sellers flow = 99% chance it's a bug**. Under normal conditions, flows are bi-directional (someone buys, someone sells). Common causes: cross-period comparison error, field mapping error, missing data source. **"Do both Buyers and Sellers have data?" must be on the checklist.**
6. **Period-over-period comparison: look at share count delta, not market value delta**. Market value changes are polluted by stock price fluctuations. Top Buyers should be ranked by "active addition" or "share count change."
7. **Carvana 2026Q1 real analysis**: Vanguard/BlackRock holdings unchanged (stable passive index capital) + Baupost added $480M (value investors re-entering) + no activist = "stable index capital + value revaluation + no activist disruption" → moderately positive state.
8. **Output quality 10-point checklist**: units, ranking metric, institution_name, delta_pct boundary, Buyers/Sellers symmetry, adjacent periods, disclaimers, staleness, Item 4 review, Chinese ADR "Not Applicable" annotation.

## Action items

- Verify: whether cross_holding.py's output follows the "each page answers one question" design (reference IHS P2-P10)
- Verify: whether the Markdown report's reading rhythm supports the 30s / 2min / 5min / 15min layered approach
- Verify: whether the 10-point checklist is automatically executed before report export (not manual check)
- Follow-up: evaluate whether to add "Commentary space" at the bottom of each Dashboard page (for analysts to write judgments)
- Follow-up: evaluate whether to unify the "period-over-period comparison" logic into a single `comparative_holdings()` function (to avoid separate implementations across different tabs)
