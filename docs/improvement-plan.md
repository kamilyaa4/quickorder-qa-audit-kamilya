# Plan d'amélioration priorisé — QuickOrder

Ces pistes sont issues du périmètre métier et de la lecture du code source. Elles doivent être validées par les tests avant d'être présentées comme corrections de bugs confirmés.

| ID | Amélioration | Justification / risque | Priorité initiale | Validation |
|---|---|---|---|---|
| IMP-01 | Vérifier le stock côté serveur à l'ajout, modification panier et checkout | Éviter commandes impossibles et stock négatif | P1 très haute | Tests stock nul et quantité supérieure au stock |
| IMP-02 | Rendre la création de commande idempotente | Éviter les doublons et double décrémentation | P1 très haute | Une seule commande pour une confirmation |
| IMP-03 | Refuser un paiement espèces inférieur au total | Cohérence du paiement simulé | P1 très haute | Montant insuffisant refusé, montant suffisant traité |
| IMP-04 | Appliquer minimum de commande et état ouvert du restaurant côté serveur | Appliquer les règles métier sur UI et API | P1 très haute | Checkout et API refusent les commandes non éligibles |
| IMP-05 | Vérifier les filtres de livraison et la recherche | Éviter des résultats trompeurs | P2 haute | Jeux de données contrôlés et résultats comparés |
| IMP-06 | Centraliser les validations métier partagées entre UI et API | Réduire les divergences et contournements | P2 haute | Mêmes règles sur interface et API |
| IMP-07 | Ajouter des tests de régression automatisés pour les parcours critiques | Détecter les régressions après correction | P2 haute | Tests sur panier, stock, checkout, coupon, autorisations |
| IMP-08 | Améliorer les messages de validation | Aider l'utilisateur à corriger une saisie | P3 moyenne | Scénarios utilisateurs et messages explicites |

## Mise en œuvre
1. Confirmer l'anomalie et son impact.
2. Corriger une anomalie à la fois dans une branche séparée si cela est autorisé.
3. Ajouter ou adapter un test de régression.
4. Rejouer les tests nominaux et négatifs concernés.
5. Consigner commit, résultat et preuve.
6. Réviser la priorité selon les observations.

Ce dépôt documente l'audit QA ; ne pas modifier le code source initial pendant la campagne initiale.
