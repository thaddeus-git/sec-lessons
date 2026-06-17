# Lernaufzeichnung 0006 — 13F und institutionelle Bestände

**Datum**: 2026-06-17
**Lektion**: 0006-13f-institutional-holdings.html
**Status**: Abgeschlossen

## Wichtige Erkenntnisse

1. **Das Wesen von 13F**: Quartalsendschnappschuss, kein Transaktionsstrom innerhalb des Quartals. Alle Zeitraumvergleiche sind "Umschichtungsnäherungen" zwischen zwei aufeinanderfolgenden 13F-Berichten – kein echter Turnover.
2. **Einheitenfalle ist eine häufige Fehlerquelle**: Das Feld `value_x1000` bedeutet "in tausend Dollar". Faktor 1000 falsch = klassischer Bug. Validierungsmethode: Kurs × Aktienanzahl ≈ value_x1000 × 1000.
3. **Bei Zeitraumvergleichen auf Aktienanzahl achten, nicht auf Marktwert**: Veränderung der Aktienanzahl = aktive Umschichtung; Wertveränderung wird durch Kursschwankungen verunreinigt. Eine Institution hält 1 Mio. CVNA-Aktien unverändert, der Kurs steigt von $100 auf $150 = passiver Wertanstieg, keine Aufstockung.
4. **Die blinden Flecken von 13F sind strukturell bedingt**: Deckt nur Longs, nur US-Aktien, nur Quartalsende, nur Institutionen >$100 Mio. Shorts, Optionen, quartalsinterne Umschichtungen, kleine Institutionen und Privatanleger sind nicht sichtbar. **Dies bestimmt, dass 13F beantworten kann "wer kauft und verkauft", aber nicht "warum".**
5. **Randbedingungen (5 Bestandsstatus)**: Initiation / Liquidation / Increase / Decrease / No change. Nach FULL OUTER JOIN institution_name ergänzen, Division durch Null bei prev_value = 0 vermeiden.
6. **Beim Zusammenfassen nach Institutionen einzeln ranken, nicht einfach SUM**: $1,92 Mrd. Bestand in Carvana vs. $3 Mio. Bestand in UXIN unterscheiden sich um Faktor 600, direkte Summierung überlagert das UXIN-Signal. Top Buyers/Sellers müssen nach "pro Ticker" oder "pro Institution" gruppiert werden.
7. **Die Seiten P2-P7 des IHS Markit-Berichts basieren fast vollständig auf 13F-Daten** – deshalb ist 13F die "Datenbasis der Cross-Holding-Analyse".

## Massnahmen

- Validierung: Prüfen, ob cross_holding.py pivot_table nach "pro Ticker" gruppiert sortiert (nicht einfaches SUM)
- Validierung: Prüfen, ob das Feld value_x1000 im gesamten Datenfluss in der ursprünglichen SEC-Einheit bleibt
- Nachverfolgung: Prüfen, ob im Dashboard eine Vergleichskarte "Aktienveränderung vs. Wertveränderung" hinzugefügt werden sollte, um Top Buyers/Sellers-Rankings genauer zu machen
