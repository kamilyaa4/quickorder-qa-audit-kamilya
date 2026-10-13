# Matrice des risques — QuickOrder

Échelle initiale : probabilité (P) de 1 à 3 × impact (I) de 1 à 3. Les scores sont des estimations à réviser après la campagne.

| ID | Risque | P | I | Score | Niveau initial | Tests associés |
|---|---|---:|---:|---:|---|---|
| R01 | Une confirmation crée plusieurs commandes | 2 | 3 | 6 | Élevé | TC-BR-04 |
| R02 | Une quantité dépasse le stock et rend le stock négatif | 3 | 3 | 9 | Critique | TC-L-02, TC-L-03, TC-BR-02 |
| R03 | Le total ou la remise est incorrect | 2 | 3 | 6 | Élevé | TC-N-05, TC-L-05 |
| R04 | Un paiement espèces inférieur au total est accepté | 2 | 3 | 6 | Élevé | TC-BR-06 |
| R05 | Une commande passe sous le minimum ou restaurant fermé | 2 | 3 | 6 | Élevé | TC-BR-03, TC-BR-05 |
| R06 | Un utilisateur accède à la commande d'un autre | 2 | 3 | 6 | Élevé | TC-E-05 |
| R07 | L'API accepte une clé absente ou invalide | 2 | 3 | 6 | Élevé | TC-E-04 |
| R08 | Les filtres de recherche retournent des résultats incorrects | 3 | 2 | 6 | Élevé | TC-N-01 |
| R09 | Un produit sans stock peut être commandé | 2 | 3 | 6 | Élevé | TC-L-03, TC-BR-02 |
| R10 | Une saisie invalide provoque une erreur non contrôlée | 2 | 2 | 4 | Moyen | TC-E-01 à TC-E-03 |
| R11 | Le statut et les détails de commande sont incohérents | 2 | 2 | 4 | Moyen | TC-N-06 |
| R12 | L'interface empêche un utilisateur d'accomplir un parcours essentiel | 2 | 2 | 4 | Moyen | Tests utilisateurs U1–U3 |

## Ordre de traitement
1. Stock, paiement, montants et doublons.
2. Autorisations et authentification API.
3. Disponibilité des produits, ouverture du restaurant et minimum de commande.
4. Recherche, filtres et navigation.
5. Ergonomie et améliorations secondaires.

Cette matrice représente les risques à vérifier, pas une liste de bugs confirmés. Ajuster les scores après observation.
