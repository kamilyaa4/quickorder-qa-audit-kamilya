# BR-CAND-04 — Une confirmation PayPal pourrait créer deux commandes

- **Statut :** Candidat à reproduire — non confirmé.
- **Source à inspecter :** `app/routes/orders.py et app/routes/api.py`
- **Préconditions :** Panier valide dans un environnement de test réinitialisable.
- **Étapes de reproduction :** 1. Noter le nombre de commandes. 2. Confirmer une fois avec PayPal simulé. 3. Recompter les commandes et vérifier le stock.
- **Résultat attendu :** Une confirmation unique devrait créer une seule commande.
- **Résultat observé :** À renseigner après exécution.
- **Preuve à collecter :** Liste des commandes et stock avant/après.
- **Sévérité / priorité :** Potentiellement élevée ; à déterminer après reproduction.

**Important :** cette fiche est issue de l'inspection du code source. Elle ne doit être présentée comme bug confirmé qu'après exécution reproductible et ajout d'une preuve. Si le comportement ne se reproduit pas, mettre à jour le statut et les conclusions.
