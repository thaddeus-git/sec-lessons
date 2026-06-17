# Lernaufzeichnung 0008 — Schedule 13D/G und Activist

**Datum**: 2026-06-17
**Lektion**: 0008-13dg-activist-investors.html
**Status**: Abgeschlossen

## Wichtige Erkenntnisse

1. **Der wesentliche Unterschied zwischen 13D und 13G liegt in der "Absicht"**: 13D = aktiver Investor (Activist), Bestand >5% und Absicht, das Unternehmen zu beeinflussen; 13G = passiver Investor (Indexfonds, Pensionskassen), reine Investition ohne Eingriff. Die Wettbewerberüberwachung interessiert sich fast ausschliesslich für 13D.
2. **13D kommt nur einige hundert Male pro Jahr vor, im Vergleich zu 13F mit 20.000 Mal/Quartal = extrem selten, aber extrem signalstark**. Jedes einzelne Mal bedeutet "jemand ist massiv bei Ihnen eingestiegen".
3. **Item 4 (Purpose of Transaction) ist die Seele von 13D**: Der Activist legt hier dar, "was ich mit diesem Unternehmen vorhabe". Häufige Absichten: Ausgliederung fordern, M&A vorantreiben, CEO-Wechsel fordern, Kapitalallokation anpassen.
4. **Kriterien zur Identifizierung eines Activists**: (1) Historische 13D-Einreichungen; (2) Proxy Fight-Aufzeichnungen; (3) Öffentliche Activist-Kampagnen; (4) Hedgefonds + konzentrierte Bestände + hohe Umschlagshäufigkeit.
5. **Häufige Activist-Strategien (nach Signalstärke sortiert)**:
   - Verwaltungsratssitze (⭐⭐⭐⭐⭐) — Offene Konfrontation mit dem Management
   - Kapitalallokation (⭐⭐⭐⭐) — Misstrauensvotum
   - M&A-Vorstoss (⭐⭐⭐⭐) — Kontrollwechsel
   - Betriebsverbesserung (⭐⭐⭐) — Signal für verborgenen Wert
6. **Die "Unumkehrbarkeit" von 13D-Einreichungen**: Sobald ein Activist öffentlich ein 13D einreicht, befinden er und der Verwaltungsrat in einem "öffentlichen Spiel" – beide Seiten müssen reagieren. Dies ist kein passives Halten, sondern eine **aktive Kriegserklärung**.
7. **Vage Formulierung in Item 4 = "Flagge zeigen und abwarten"-Activist**: Möglicherweise nur Positionsaufbau ohne echten Kampf. In den folgenden 60-90 Tagen auf ergänzende 13D / Proxy Fight / öffentliche Kandidatennominierung achten.
8. **Besonderheit chinesischer ADRs**: UXIN ist ein ADR, daher gilt 13D/G, aber geringe Liquidität + chinesischer Verwaltungsrat + rechtliche Unterschiede → tatsächliche Durchsetzungsfähigkeit von Activists begrenzt. Einmaliges Auftreten ist umso stärkeres Signal (seltenes Ereignis).
9. **Unsere derzeitige Lücke vs. IHS**: Statische Liste 8 Institutionen vs. IHS ~50-100. Zur Schliessung ist der Kauf von WhaleWisdom / SharkWatch oder die manuelle monatliche Durchsicht der EDGAR 13D-Berichte erforderlich. MVP-Phase: Kombination aus "8 Institutionen + manuelle monatliche Durchsicht + Alarm bei neuem Activist" ist am wirtschaftlichsten.

## Massnahmen

- Validierung: Prüfen, ob die ACTIVIST_INSTITUTIONS-Liste in config.py bekannte Mainstream-Activists enthält (Elliott, Starboard, Third Point, Baupost, Pershing Square usw.)
- Validierung: Prüfen, ob der "Activists"-Reiter im Dashboard eine separate Seite ist (nicht mit anderen Institutionen vermischt)
- Validierung: Prüfen, ob die Extraktion von 13D Item 4 automatisch oder manuell erfolgt (MVP sollte manuelle Überprüfung + Hervorhebung sein)
- Nachverfolgung: ROI der günstigsten WhaleWisdom-Stufe bewerten ($500-2000/Jahr)
- Nachverfolgung: Prüfen, ob ein automatischer "neuer Activist"-Alarm eingerichtet werden sollte (basierend auf EDGAR 13D-Monatsbericht + Keyword-Filter)
