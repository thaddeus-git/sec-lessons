# Learning Record 0009 — Méthodologie d'Analyse des Participations Croisées

**Date** : 2026-06-17
**Leçon** : 0009-cross-holding-methodology.html
**Statut** : Terminé

## Points clés

1. **Chaque page répond à une question d'investissement spécifique** : c'est la philosophie centrale de conception du rapport de participations croisées. Les 10 pages du rapport IHS P4 = 10 questions. Entasser des données ≠ faire un rapport.
2. **La validation croisée entre pages est la véritable source d'intelligence**. 4 scénarios classiques :
   - Confirmatif (P2 forte détention + P3 renforcement + P5 Top Buyer) = signal fort
   - Contradictoire (P2 forte détention + P3 léger désengagement + P6 non Top Seller) = probable rééquilibrage
   - Dangereux (P4 activiste + P7 nouvelle position) = alerte élevée
   - Virage (P8 hausse des capitaux passifs + P9 rotation valeur/croissance) = changement de cycle sectoriel
3. **Ordre de lecture correct du rapport** : survol 30 secondes → tendances 2 minutes → analyse approfondie 5 minutes → recherche 15 minutes. La conception du Dashboard doit soutenir ce rythme (cartes de synthèse les plus visibles, données approfondies cachées dans des onglets).
4. **6 principes de conception** :
   - Chaque page répond à une question
   - Chaque page laisse un espace « Commentaire » en bas (pour que l'analyste note son jugement)
   - Les colonnes des tableaux doivent être alignées sur les standards du secteur (Style / Turnover / Peer Average : les trois sont indispensables)
   - Les classements doivent impérativement indiquer la métrique de classement
   - Graphiques et tableaux doivent être appariés (camembert pour la répartition, histogramme pour les flux)
   - Les mentions légales doivent être visibles (en bas de chaque page, pas à la fin du document)
5. **Un flux unidirectionnel des Top Buyers/Sellers = 99 % de chances d'être un bug**. Dans des conditions normales, les flux sont bidirectionnels (certains achètent, d'autres vendent). Causes fréquentes : erreur de comparaison interpériode, erreur de correspondance de champs, source de données manquante. **La checklist d'auto-vérification doit impérativement inclure « Les Buyers et les Sellers ont-ils tous des données ? »**.
6. **Comparaison interpériode : regarder le nombre d'actions (shares delta), pas la valeur (value delta)**. La variation de la valeur est polluée par les fluctuations du cours. Le classement des Top Buyers doit se faire selon le « renforcement actif » ou la « variation du nombre d'actions ».
7. **Analyse pratique Carvana 2026 T1** : Vanguard/BlackRock inchangés (stabilité des capitaux indiciels passifs) + Baupost nouvelle position de 480 M$ (retour d'un investisseur value) + pas d'activiste = « stabilité indicielle + réévaluation value + aucune interférence activiste » → situation plutôt positive.
8. **Checklist d'auto-vérification en 10 points pour la qualité des livrables** : unités, métrique de classement, institution_name, limites de delta_pct, symétrie Buyers/Sellers, contiguïté interpériode, mentions légales, décalage temporel, review de l'Item 4, mention « Non applicable » pour les ADR chinois.

## Actions à mener

- Vérifier : les livrables de cross_holding.py respectent-ils la conception « chaque page répond à une question » (en référence aux pages IHS P2-P10) ?
- Vérifier : le rythme de lecture du rapport Markdown prend-il en charge les niveaux 30 secondes / 2 minutes / 5 minutes / 15 minutes ?
- Vérifier : les 10 points de la checklist d'auto-vérification sont-ils exécutés automatiquement avant l'export du rapport (pas manuellement) ?
- Suivi : faut-il ajouter un espace « Commentaire » en bas de chaque page du Dashboard (pour que l'analyste note son jugement) ?
- Suivi : évaluer s'il faut unifier la logique de « comparaison interpériode » dans une fonction `comparative_holdings()` (pour éviter des implémentations différentes selon les onglets).
