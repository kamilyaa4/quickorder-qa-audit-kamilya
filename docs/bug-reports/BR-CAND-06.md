# BR-CAND-06 — Paiement espèces potentiellement accepté si montant insuffisant

- **Statut :** Observation consignée dans TC-BR-06 ; à confirmer avec une preuve accessible.
- **Source à inspecter :** `app/routes/orders.py`.
- **Préconditions :** Panier valide et paiement en espèces disponible.
- **Étapes de reproduction :**
  1. Relever le total exact du panier.
  2. Saisir un montant reçu inférieur au total.
  3. Confirmer le parcours de commande.
  4. Vérifier l'état final de la commande.
- **Résultat attendu :** La commande ne devrait pas être confirmée si le montant reçu est insuffisant, selon la règle métier prévue.
- **Résultat observé consigné :** Le tableau indique que la commande a été confirmée malgré un montant insuffisant.
- **Preuve référencée :** `test18.png` dans le CSV ; cette capture n'a pas été retrouvée dans `evidence/` lors de la vérification du dépôt.
- **Sévérité / priorité proposée :** Majeure, P1, si l'observation est reproduite.
- **Cas associé :** TC-BR-06.

**Limite :** vérifier la règle métier exacte du paiement simulé et joindre une capture réelle du montant saisi et de l'état de commande avant de considérer la preuve comme jointe.
