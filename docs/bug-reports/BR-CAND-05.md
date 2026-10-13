# BR-CAND-05 — Minimum de commande potentiellement non appliqué au checkout

- **Statut :** Candidat à reproduire — non confirmé.
- **Source à inspecter :** `app/routes/orders.py`
- **Préconditions :** Minimum du restaurant supérieur au sous-total du panier.
- **Étapes de reproduction :** 1. Composer un panier inférieur au minimum. 2. Ouvrir checkout. 3. Tenter de confirmer.
- **Résultat attendu :** La confirmation devrait être bloquée avec une explication du minimum requis.
- **Résultat observé :** À renseigner après exécution.
- **Preuve à collecter :** Capture du checkout et résultat de commande.
- **Sévérité / priorité :** À déterminer après reproduction.

**Important :** cette fiche est issue de l'inspection du code source. Elle ne doit être présentée comme bug confirmé qu'après exécution reproductible et ajout d'une preuve. Si le comportement ne se reproduit pas, mettre à jour le statut et les conclusions.
