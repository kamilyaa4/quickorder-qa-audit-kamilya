# BR-CAND-03 — Quantité du panier potentiellement supérieure au stock

- **Statut :** Candidat à reproduire — non confirmé.
- **Source à inspecter :** `app/routes/shop.py`
- **Préconditions :** Connaître le stock d'un produit de test.
- **Étapes de reproduction :** 1. Ajouter le produit. 2. Modifier la quantité au-delà du stock. 3. Tenter de confirmer.
- **Résultat attendu :** La quantité devrait être refusée ou limitée au stock ; le stock ne devrait jamais devenir négatif.
- **Résultat observé :** À renseigner après exécution.
- **Preuve à collecter :** Capture du panier et stock avant/après.
- **Sévérité / priorité :** À déterminer après reproduction.

**Important :** cette fiche est issue de l'inspection du code source. Elle ne doit être présentée comme bug confirmé qu'après exécution reproductible et ajout d'une preuve. Si le comportement ne se reproduit pas, mettre à jour le statut et les conclusions.
