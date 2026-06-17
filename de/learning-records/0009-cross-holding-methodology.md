# Lernaufzeichnung 0009 — Methodik der Cross-Holding-Analyse

**Datum**: 2026-06-17
**Lektion**: 0009-cross-holding-methodology.html
**Status**: Abgeschlossen

## Wichtige Erkenntnisse

1. **Jede Seite beantwortet eine spezifische Anlagefrage** ist die zentrale Designphilosophie eines Cross-Holding-Berichts. Die 10 Seiten des IHS P4-Berichts = 10 Fragen. Daten anhäufen ≠ Bericht.
2. **Seitenübergreifende Kreuzvalidierung ist die wahre Einsicht**. 4 klassische Szenarien:
   - Bestätigend (P2 grosser Bestand + P3 Aufstockung + P5 Top Buyer) = starkes Signal
   - Widersprüchlich (P2 grosser Bestand + P3 kleine Reduktion + P6 kein Top Seller) = könnte Neugewichtung sein
   - Gefährlich (P4 Activist + P7 Neupositionierung) = hohe Alarmstufe
   - Trendwende (P8 passives Kapital steigt + P9 Value/Growth-Rotation) = Veränderung des Branchenlebenszyklus
3. **Richtige Lesereihenfolge des Berichts**: 30 Sekunden Überblick → 2 Minuten Trend → 5 Minuten Tiefe → 15 Minuten Forschung. Dashboard-Design sollte diesen Rhythmus unterstützen (Übersichtskarten am prominentesten, Tiefendaten in Registerkarten).
4. **6 Designprinzipien**:
   - Jede Seite beantwortet eine Frage
   - Jede Seite hat unten Platz für Kommentare (für die Analyse des Analysten)
   - Tabellenspalten an branchenübliche Standards anpassen (Style / Turnover / Peer Average unverzichtbar)
   - Ranking-Tabellen müssen die Ranking-Kennzahl angeben
   - Diagramme und Tabellen zusammenführen (Kuchendiagramm für Verteilung, Balkendiagramm für Ströme)
   - Haftungsausschluss muss sichtbar sein (auf jeder Seite, nicht am Dokumentende)
5. **Einseitiger Fluss bei Top Buyers/Sellers = zu 99% ein Bug**. Normalerweise zweiseitig (jemand kauft, jemand verkauft). Häufige Ursachen: Zeitraumvergleich fehlerhaft, Feldzuordnung falsch, Datenquelle unvollständig. **Checkliste muss enthalten: "Haben Buyers und Sellers beide Daten?"**.
6. **Bei Zeitraumvergleichen auf Aktienveränderung (shares delta) achten, nicht auf Wertveränderung (value delta)**. Wertveränderungen werden durch Kursschwankungen verunreinigt. Top Buyers sollten nach "aktiver Aufstockung" oder "Aktienveränderung" sortiert werden.
7. **Praktische Analyse von Carvana 2026Q1**: Vanguard/BlackRock Bestände unverändert (stabile passive Indexgelder) + Baupost neu $480 Mio. (Value-Investoren steigen wieder ein) + kein Activist = "Index stabil + Neubewertung + keine Activist-Störung" → eher positives Bild.
8. **10-Punkte-Checkliste für Ausgabequalität**: Einheiten, Ranking-Kennzahlen, institution_name, delta_pct Grenzen, Buyers/Sellers Symmetrie, Zeitraum benachbart, Haftungsausschluss, Datenverzögerung, Item 4 Überprüfung, chinesische ADR "nicht zutreffend"-Kennzeichnung.

## Massnahmen

- Validierung: Prüfen, ob der Output von cross_holding.py dem Design "jede Seite beantwortet eine Frage" entspricht (Referenz IHS P2-P10)
- Validierung: Prüfen, ob der Leserhythmus des Markdown-Berichts die 30-Sekunden-/2-Minuten-/5-Minuten-/15-Minuten-Ebenen unterstützt
- Validierung: Prüfen, ob die 10-Punkte-Checkliste vor dem Export des Berichts automatisch ausgeführt wird (nicht manuell)
- Nachverfolgung: Prüfen, ob "Kommentarbereich" am Ende jeder Dashboard-Seite hinzugefügt werden sollte (Platz für die Analyse des Analysten)
- Nachverfolgung: Prüfen, ob die "Zeitraumvergleichslogik" in einer einzigen Funktion `comparative_holdings()` vereinheitlicht werden sollte (um unterschiedliche Implementierungen in verschiedenen Registerkarten zu vermeiden)
