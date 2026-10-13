# BR-CAND-02 — Produit à stock nul potentiellement visible ou ajoutable

- **Statut :** Candidat à reproduire — non confirmé.
- **Source à inspecter :** `app/routes/main.py et app/routes/shop.py`
- **Préconditions :** Produit de test avec stock 0 et indicateur disponible.
- **Étapes de reproduction :** 1. Ouvrir le restaurant. 2. Rechercher le produit. 3. Tenter de l'ajouter au panier.
- **Résultat attendu :** Un produit en rupture ne devrait pas pouvoir être commandé.
- **Résultat observé :** À renseigner après exécution.
- **Preuve à collecter :** Capture du menu, panier et stock avant/après.
- **Sévérité / priorité :** À déterminer après reproduction.

**Important :** cette fiche est issue de l'inspection du code source. Elle ne doit être présentée comme bug confirmé qu'après exécution reproductible et ajout d'une preuve. Si le comportement ne se reproduit pas, mettre à jour le statut et les conclusions.
