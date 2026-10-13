# BR-CAND-06 — Paiement espèces potentiellement accepté avec un montant insuffisant

- **Statut :** Candidat à reproduire — non confirmé.
- **Source à inspecter :** `app/routes/orders.py`
- **Préconditions :** Panier valide et option espèces disponible.
- **Étapes de reproduction :** 1. Relever le total. 2. Saisir un montant inférieur. 3. Confirmer. 4. Vérifier l'état de la commande.
- **Résultat attendu :** La commande ne devrait pas être confirmée si le montant reçu est inférieur au total.
- **Résultat observé :** À renseigner après exécution.
- **Preuve à collecter :** Capture du formulaire et détail de commande.
- **Sévérité / priorité :** Potentiellement élevée ; à déterminer après reproduction.

**Important :** cette fiche est issue de l'inspection du code source. Elle ne doit être présentée comme bug confirmé qu'après exécution reproductible et ajout d'une preuve. Si le comportement ne se reproduit pas, mettre à jour le statut et les conclusions.
