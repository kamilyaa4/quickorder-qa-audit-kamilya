# Plan d'amélioration priorisé — QuickOrder

Ces pistes sont issues du périmètre métier et de la lecture du code source. Elles doivent être validées par les tests avant d'être présentées comme corrections de bugs confirmés.

## Améliorations proposées

| Priorité | Problème constaté | Amélioration proposée | Anomalie liée |
| -------- | ----------------- | --------------------- | ------------- |
| P1 | Un produit en rupture peut être ajouté au panier | Bloquer l'ajout quand le stock est à 0 et vérifier le stock à la confirmation de commande | BR-CAND-02 |
| P1 | Une commande passe sous le minimum de commande | Vérifier le minimum côté serveur avant de confirmer la commande | BR-CAND-05 |
| P1 | Une commande est confirmée avec un montant en espèces insuffisant | Refuser la confirmation tant que le montant reçu est inférieur au total | BR-CAND-06 |
| P2 | L'API accepte une commande sans articles (201) | Valider le corps de la requête et renvoyer 400 avec un message explicite | BR-10 |
| P2 | Un produit d'un restaurant fermé peut être ajouté au panier | Vérifier l'ouverture du restaurant avant l'ajout et à la commande | BR-11 |
| P2 | Le filtre par catégorie ne filtre pas | Corriger la requête de filtre sur la page d'accueil | BR-09 |

## Re-test après correction

Après chaque correction, rejouer le cas associé (TC-L-02, TC-BR-02, TC-BR-05, TC-BR-06, TC-E-03, TC-BR-03, TC-N-01), puis les cas de régression (TC-N-04, TC-N-05, TC-BR-04), et noter le résultat et la preuve.
Ce dépôt documente l'audit QA ; ne pas modifier le code source initial pendant la campagne initiale.
