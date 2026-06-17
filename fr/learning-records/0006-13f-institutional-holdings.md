# Learning Record 0006 — 13F et Participations Institutionnelles

**Date** : 2026-06-17
**Leçon** : 0006-13f-institutional-holdings.html
**Statut** : Terminé

## Points clés

1. **L'essence du 13F** : un instantané de fin de trimestre, pas un flux intra-trimestriel. Toute comparaison interpériode est une « approximation de réallocation » entre deux 13F consécutifs — pas un turnover réel.
2. **Le piège des unités est une source majeure de bugs** : le champ `value_x1000` signifie « en milliers de dollars ». Se tromper d'un facteur 1000 est une erreur classique. Méthode de vérification : cours × nombre d'actions ≈ value_x1000 × 1000.
3. **Comparaison interpériode : regarder le nombre d'actions, pas la valeur** : la variation du nombre d'actions = réallocation active ; la variation de la valeur est polluée par les fluctuations du cours. Un institution détenant 1 million d'actions CVNA inchangées alors que le cours passe de 100 $ à 150 $ = hausse passive de la valeur, pas un renforcement de position.
4. **Les angles morts du 13F sont des contraintes structurelles** : il ne couvre que les positions longues, que les actions américaines, que la fin de trimestre, et uniquement les institutions >100 M$. Pas de visibilité sur les ventes à découvert, les options, les réallocations intra-trimestre, les petites institutions ni les particuliers. **Cela détermine que le 13F peut répondre à « qui achète/vend », mais pas à « pourquoi »**.
5. **Cas limites (5 états de détention)** : Initiation / Liquidation / Augmentation / Diminution / Pas de changement. Après un FULL OUTER JOIN, compléter avec institution_name pour éviter la division par zéro lorsque prev_value = 0.
6. **Le classement par institution lors de l'agrégation ne peut pas être une simple SOMME** : les 1,92 Md$ de positions sur Carvana vs les 3 M$ sur UXIN — un rapport de 600x — noierait le signal d'UXIN. Les Top Buyers/Sellers doivent être regroupés « par ticker » ou « par institution ».
7. **Les pages P2-P7 du rapport IHS Markit reposent presque entièrement sur les données 13F** — c'est pourquoi le 13F est le « socle de données de l'analyse des participations croisées ».

## Actions à mener

- Vérifier : le pivot_table de cross_holding.py est-il trié par groupe « par ticker » (pas une simple SOMME) ?
- Vérifier : le champ value_x1000 conserve-t-il l'unité SEC d'origine dans tout le flux de données ?
- Suivi : envisager d'ajouter sur le Dashboard une carte de comparaison « variation du nombre d'actions vs variation de la valeur » pour un classement plus précis des Top Buyers/Sellers.
