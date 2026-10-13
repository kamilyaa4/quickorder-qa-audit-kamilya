# BR-CAND-07 — API de commande susceptible d'ignorer le stock

- **Statut :** Candidat à reproduire — non confirmé.
- **Source à inspecter :** `app/routes/api.py, POST /orders`
- **Préconditions :** Clé API valide et produit avec stock connu.
- **Étapes de reproduction :** 1. Envoyer une commande dont la quantité dépasse le stock. 2. Vérifier statut HTTP, JSON et stock.
- **Résultat attendu :** L'API devrait refuser la quantité excédentaire et ne jamais rendre le stock négatif.
- **Résultat observé :** À renseigner après exécution.
- **Preuve à collecter :** Requête/réponse Swagger et stock avant/après.
- **Sévérité / priorité :** Potentiellement élevée ; à déterminer après reproduction.

**Important :** cette fiche est issue de l'inspection du code source. Elle ne doit être présentée comme bug confirmé qu'après exécution reproductible et ajout d'une preuve. Si le comportement ne se reproduit pas, mettre à jour le statut et les conclusions.
