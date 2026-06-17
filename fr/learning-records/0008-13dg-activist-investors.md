# Learning Record 0008 — Schedule 13D/G et Investisseurs Activistes

**Date** : 2026-06-17
**Leçon** : 0008-13dg-activist-investors.html
**Statut** : Terminé

## Points clés

1. **La différence essentielle entre 13D et 13G réside dans « l'intention »** : 13D = investisseur activiste, détention >5 % avec l'intention d'influencer l'entreprise ; 13G = investisseur passif (fonds indiciels, fonds de pension), pur investissement sans ingérence dans la gestion. La surveillance concurrentielle ne concerne quasiment que le 13D.
2. **Il n'y a que quelques centaines de 13D par an, contre environ 20 000 13F par trimestre = extrêmement rare mais signal extrêmement fort**. Chaque occurrence signifie « quelqu'un a constitué une position importante chez vous ».
3. **L'Item 4 (Purpose of Transaction) est l'âme du 13D** : l'activiste y explique « ce que j'ai l'intention de faire avec cette entreprise ». Intentions courantes : exiger une scission, pousser à une fusion-acquisition, exiger le remplacement du PDG, exiger un réajustement de l'allocation du capital.
4. **Critères pour identifier un activiste** : ① historique de dépôts 13D ; ② historique de proxy fight ; ③ campagne activiste publique ; ④ hedge fund + positions concentrées + forte rotation.
5. **Stratégies activistes courantes (classées par intensité du signal)** :
   - Siège au conseil d'administration (⭐⭐⭐⭐⭐) — confrontation publique avec la direction
   - Allocation du capital (⭐⭐⭐⭐) — vote de défiance
   - Poussée M&A (⭐⭐⭐⭐) — changement de contrôle
   - Amélioration opérationnelle (⭐⭐⭐) — signal de valeur cachée
6. **L'« irréversibilité » du dépôt 13D** : une fois le 13D déposé publiquement, l'activiste et le conseil d'administration entrent dans un « jeu public » — les deux parties doivent répondre. Ce n'est pas une détention passive, c'est une **déclaration de guerre active**.
7. **Un libellé flou à l'Item 4 = activiste de type « lever le drapeau d'abord, observer ensuite »** : il s'agit peut-être simplement d'une occupation de terrain pour faire pression, sans réelle intention d'engager le combat. Il faut surveiller les 60 à 90 jours suivants pour un éventuel 13D complémentaire / proxy fight / nomination publique d'administrateur.
8. **Spécificité des ADR chinois** : UXIN étant un ADR, le 13D/G s'applique, mais la faible liquidité + le conseil d'administration chinois + les différences d'environnement juridique → capacité réelle de l'activiste limitée. Une apparition est d'autant plus un signal fort (événement rare).
9. **Notre écart actuel par rapport à IHS** : 8 noms dans notre liste statique contre ~50-100 chez IHS. Pour combler cet écart, il faudrait acquérir WhaleWisdom / SharkWatch ou effectuer un balayage manuel mensuel des rapports 13D sur EDGAR. La combinaison la plus économique en phase MVP est « 8 noms + balayage manuel mensuel + alerte en cas d'apparition d'un nouvel activiste ».

## Actions à mener

- Vérifier : la liste ACTIVIST_INSTITUTIONS dans config.py inclut-elle les activistes majeurs (Elliott, Starboard, Third Point, Baupost, Pershing Square, etc.) ?
- Vérifier : l'onglet « Activists » du Dashboard est-il sur une page séparée (pas mélangé avec les autres institutions) ?
- Vérifier : l'extraction de l'Item 4 du 13D est-elle automatique ou manuelle ? (MVP devrait être review manuel + mise en évidence)
- Suivi : évaluer le ROI du tier le plus bas de WhaleWisdom (500-2000 $/an).
- Suivi : faut-il mettre en place une alerte automatique « nouvel activiste détecté » (basée sur les rapports mensuels 13D EDGAR + filtrage par mots-clés) ?
