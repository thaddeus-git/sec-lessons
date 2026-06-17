# Learning Record 0007 — Formulaires 3/4/5 et Transactions d'Initiés

**Date** : 2026-06-17
**Leçon** : 0007-form4-insider-trading.html
**Statut** : Terminé

## Points clés

1. **Périmètre d'application de la Section 16** : ne couvre que les initiés détenant des <strong>titres enregistrés aux États-Unis</strong>. Les dirigeants d'ADR chinois (UXIN/ATHM) détiennent généralement des parts au niveau du VIE → non applicable. Donc « pas de données » ≠ « échec de collecte », c'est une « non-applicabilité » structurelle.
2. **Différence entre les trois formulaires** : Formulaire 3 (déclaration initiale, unique) / Formulaire 4 (chaque transaction, 2 jours ouvrés, le plus important) / Formulaire 5 (récapitulatif annuel, transactions exonérées).
3. **Tableau I vs Tableau II** : Tableau I = actions directes ; Tableau II = options/dérivés. M (exercice) + F (vente pour impôts) = opération couplée, pas un signal baissier.
4. **Pondération des codes de transaction** :
   - P (achat actif) = 1,0 (signal fort)
   - S (vente active) = 1,0
   - F (vente pour impôts) = 0,2 (signal faible conservé)
   - G (donation) = 0,3
   - A (attribution) = 0,0 (pas une transaction active)
   - M (exercice) = 0,0 (ne regarder que les ventes après exercice)
5. **Pondération des rôles** : PDG/CFO = 2,0 (le plus sensible) / Propriétaire à 10 % = 1,5 / Administrateur = 1,0 / EVP/SVP/VP = 0,8.
6. **Le plan 10b5-1 est la plus grande source d'erreur d'interprétation** : les plans de transaction préétablis des dirigeants génèrent de nombreuses paires Code F/S. **L'analyse doit impérativement vérifier la date de dépôt du plan 10b5-1** (dans le 8-K Item 8.01 ou DEF 14A), pas la transaction elle-même.
7. **Le Formulaire 144 est une « bande-annonce »** : notification préalable, pas une divulgation ultérieure. « Prévu pour vendre dans 90 jours » ≠ « déjà vendu ». Des soumissions multiples et consécutives de Formulaire 144 = signal de cession continue.
8. **Règle d'alerte pour les ADR chinois** : si un Formulaire 4 apparaît soudainement pour UXIN/ATHM → c'est un signal extrêmement important (événement rare), le système doit déclencher une alerte rouge.

## Actions à mener

- Vérifier : insider_tracker.py implémente-t-il l'algorithme de pondération InsiderSentiment (pondération du rôle × pondération du code de transaction) ?
- Vérifier : sur le Dashboard, les concurrents ADR chinois affichent-ils « Non applicable » + une note explicative (pas « Pas de données ») ?
- Suivi : faut-il ajouter au système le suivi de la date de dépôt des plans 10b5-1 (ROI élevé, peut réduire 80 % des erreurs d'interprétation) ?
- Suivi : source de données du « taux d'exécution réel » du Formulaire 144 (OpenInsider dispose de ces données).
