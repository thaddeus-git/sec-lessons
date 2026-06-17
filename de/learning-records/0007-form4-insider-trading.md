# Lernaufzeichnung 0007 — Form 3/4/5 und Insiderhandel

**Datum**: 2026-06-17
**Lektion**: 0007-form4-insider-trading.html
**Status**: Abgeschlossen

## Wichtige Erkenntnisse

1. **Anwendungsbereich von Section 16**: Deckt nur Insider ab, die <strong>US-registrierte Wertpapiere</strong> halten. Führungskräfte chinesischer ADRs (UXIN/ATHM) halten in der Regel Anteile auf VIE-Ebene → nicht anwendbar. Daher bedeutet "keine Daten" ≠ "Erfassungsfehler", sondern strukturell "nicht zutreffend".
2. **Unterschiede der drei Formulare**: Form 3 (erstmalige Erklärung, einmalig) / Form 4 (jede Transaktion, 2 Werktage, am wichtigsten) / Form 5 (Jahreszusammenfassung, ausgenommene Transaktionen).
3. **Table I vs Table II**: Table I = Direktbeteiligung; Table II = Optionen/Derivate. M (Ausübung) + F (Steuerverkauf) = Paartransaktion, kein bärisches Signal.
4. **Gewichtung der Transaktionscodes**:
   - P (aktiver Kauf) = 1,0 (starkes Signal)
   - S (aktiver Verkauf) = 1,0
   - F (Steuerverkauf) = 0,2 (schwaches Signal erhalten)
   - G (Schenkung) = 0,3
   - A (Zuteilung) = 0,0 (gilt nicht als aktive Transaktion)
   - M (Ausübung) = 0,0 (nur auf Verkäufe nach Ausübung achten)
5. **Rollengewichte**: CEO/CFO = 2,0 (sensibelste) / 10% Owner = 1,5 / Director = 1,0 / EVP/SVP/VP = 0,8.
6. **10b5-1 Pläne sind die grösste Fehlerquelle**: Von Führungskräften voreingestellte Handelspläne erzeugen massenhaft gepaarte Code F/S Transaktionen. **Bei der Beurteilung muss das Einreichungsdatum des 10b5-1 Plans beachtet werden** (in 8-K Item 8.01 oder DEF 14A), nicht die Transaktionen selbst.
7. **Form 144 ist der "Trailer"**: Vorabmitteilung, keine nachträgliche Offenlegung. "Geplanter Verkauf innerhalb von 90 Tagen" ≠ "bereits verkauft". Mehrere aufeinanderfolgende Form 144-Einreichungen = anhaltendes Verkaufssignal.
8. **Alarmregel für chinesische ADR-Anomalien**: Wenn UXIN/ATHM plötzlich Form 4 zeigen → extrem wichtiges Signal (seltenes Ereignis), das System sollte einen roten Alarm auslösen.

## Massnahmen

- Validierung: Prüfen, ob insider_tracker.py den gewichteten InsiderSentiment-Algorithmus implementiert (Rollengewicht × Transaktionscode-Gewicht)
- Validierung: Prüfen, ob im Dashboard bei chinesischen ADR-Wettbewerbern "nicht zutreffend" + Hinweis angezeigt wird (nicht "keine Daten")
- Nachverfolgung: Prüfen, ob das Einreichungsdatum von 10b5-1 Plänen ins System aufgenommen werden sollte (hoher ROI, reduziert 80% der Fehlurteile)
- Nachverfolgung: Datenquelle für die "tatsächliche Ausführungsrate" von Form 144 (OpenInsider hat diese Daten)
