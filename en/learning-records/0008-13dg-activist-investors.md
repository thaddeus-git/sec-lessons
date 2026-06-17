# Learning Record 0008 — Schedule 13D/G & Activist Investors

**Date**: 2026-06-17
**Lesson**: 0008-13dg-activist-investors.html
**Status**: Completed

## Key insights

1. **The essential difference between 13D and 13G is "intent"**: 13D = active investors (activists), ownership >5% with intent to influence the company; 13G = passive investors (index funds, pensions), pure investment without operational intervention. Competitor monitoring is almost exclusively concerned with 13D.
2. **13D filings occur only a few hundred times per year, compared to 13F's 20,000+ per quarter = extremely rare but extremely high signal**. Each one represents "someone has built a large position in your company."
3. **Item 4 (Purpose of Transaction) is the soul of the 13D**: the activist states "why I bought this company." Common intents: demand a spin-off, push M&A, demand CEO replacement, demand capital allocation changes.
4. **Criteria for identifying an activist**: (1) History of 13D filings; (2) proxy fight history; (3) public activist campaigns; (4) hedge fund + concentrated holdings + high turnover.
5. **Common activist strategies (ranked by signal strength)**:
   - Board seats (⭐⭐⭐⭐⭐) -- open confrontation with management
   - Capital allocation (⭐⭐⭐⭐) -- vote of no confidence
   - M&A push (⭐⭐⭐⭐) -- change of control
   - Operational improvement (⭐⭐⭐) -- hidden value signal
6. **The "irreversibility" of a 13D filing**: once a 13D is publicly filed, the activist and the board enter a "public game" -- both sides must respond. This is not passive holding; it is **open warfare**.
7. **Vague Item 4 wording = "plant the flag, then watch" activist**: may just be taking a position to apply pressure without a real fight. Watch for supplemental 13D / proxy fight / public director nominations in the following 60-90 days.
8. **Chinese ADR specifics**: UXIN is an ADR so 13D/G applies, but poor liquidity + Chinese board + legal environment differences → activist's actual ability to drive change is limited. A single occurrence is actually a stronger signal (rare event).
9. **Our gap vs IHS**: static list of 8 vs IHS ~50-100. Closing this requires purchasing WhaleWisdom / SharkWatch or manually scanning EDGAR 13D monthly. In the MVP phase, "8 firms + manual monthly scan + new activist alert" is the most economical combination.

## Action items

- Verify: whether config.py's ACTIVIST_INSTITUTIONS list includes mainstream activists (Elliott, Starboard, Third Point, Baupost, Pershing Square, etc.)
- Verify: whether the Dashboard "Activists" Tab is on its own page (not mixed with other institutions)
- Verify: whether 13D Item 4 extraction is automated or manual (MVP should be manual review + highlighted display)
- Follow-up: evaluate the ROI of purchasing WhaleWisdom's lowest tier ($500-2000/year)
- Follow-up: consider building an automatic "new activist detected" alert (based on EDGAR 13D monthly report + keyword filtering)
