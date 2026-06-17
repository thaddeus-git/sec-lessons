# Learning Record 0007 — Form 3/4/5 & Insider Trading

**Date**: 2026-06-17
**Lesson**: 0007-form4-insider-trading.html
**Status**: Completed

## Key insights

1. **Section 16 Applicability**: only covers insiders holding <strong>U.S. registered securities</strong>. Chinese ADR (UXIN/ATHM) executives typically hold VIE-level interests → not applicable. So "no data" ≠ "collection failure," it is a structural "Not Applicable."
2. **Difference between the three forms**: Form 3 (initial statement, one-time) / Form 4 (every transaction, 2 business days, most important) / Form 5 (annual summary, exempt transactions).
3. **Table I vs Table II**: Table I = direct holdings; Table II = options/derivatives. M (exercise) + F (tax withholding) = paired operation, not a bearish signal.
4. **Transaction code weight design**:
   - P (open market purchase) = 1.0 (strong signal)
   - S (open market sale) = 1.0
   - F (tax withholding) = 0.2 (retains faint signal)
   - G (gift) = 0.3
   - A (award) = 0.0 (not active trading)
   - M (exercise) = 0.0 (only look at post-exercise sales)
5. **Role weights**: CEO/CFO = 2.0 (most sensitive) / 10% Owner = 1.5 / Director = 1.0 / EVP/SVP/VP = 0.8.
6. **10b5-1 plans are the biggest source of misjudgment**: preset trading plans generate large volumes of paired Code F/S. **Judgment must check the 10b5-1 plan filing date** (in 8-K Item 8.01 or DEF 14A), not the trades themselves.
7. **Form 144 is a "trailer"**: advance notice, not after-the-fact disclosure. "Plans to sell within 90 days" ≠ "already sold." Multiple consecutive Form 144 filings = sustained selling signal.
8. **Chinese ADR anomaly alert rule**: if UXIN/ATHM suddenly have Form 4 data → this is an extremely important signal (rare event), the system should trigger a red alert.

## Action items

- Verify: whether insider_tracker.py implements the InsiderSentiment weighted algorithm (role weight × transaction code weight)
- Verify: whether the Dashboard shows "Not Applicable" + annotation for Chinese ADR competitors (not "No Data")
- Follow-up: evaluate whether to add 10b5-1 plan filing date tracking to the system (high ROI, reduces 80% of misjudgments)
- Follow-up: Form 144 "actual execution rate" data source (OpenInsider has this data)
