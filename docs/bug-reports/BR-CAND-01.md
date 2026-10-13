# BR-CAND-01 — Filtre des frais de livraison potentiellement inversé

- **Statut :** Candidat à reproduire — non confirmé.
- **Source à inspecter :** `app/routes/main.py`
- **Préconditions :** Avoir plusieurs restaurants avec des frais de livraison différents.
- **Étapes de reproduction :** 1. Ouvrir l'accueil. 2. Définir un maximum de frais, par exemple 2,50 €. 3. Comparer les frais des restaurants affichés.
- **Résultat attendu :** Seuls les restaurants dont les frais sont inférieurs ou égaux au maximum devraient apparaître.
- **Résultat observé :** À renseigner après exécution.
- **Preuve à collecter :** Capture d'écran et URL des filtres.
- **Sévérité / priorité :** À déterminer après reproduction.

**Important :** cette fiche est issue de l'inspection du code source. Elle ne doit être présentée comme bug confirmé qu'après exécution reproductible et ajout d'une preuve. Si le comportement ne se reproduit pas, mettre à jour le statut et les conclusions.
