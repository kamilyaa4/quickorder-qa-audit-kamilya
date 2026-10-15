# BR-CAND-05 — Minimum de commande potentiellement non appliqué au checkout

- **Statut :** Observation consignée dans TC-BR-05 ; à confirmer avec une preuve accessible.
- **Source à inspecter :** `app/routes/orders.py`.
- **Préconditions :** Minimum du restaurant supérieur au sous-total.
- **Étapes de reproduction :**
  1. Choisir un restaurant avec un minimum de commande connu.
  2. Composer un panier inférieur au minimum.
  3. Ouvrir le checkout.
  4. Tenter de confirmer la commande.
  5. Vérifier si une commande a effectivement été créée.
- **Résultat attendu :** La confirmation devrait être bloquée et le minimum requis expliqué.
- **Résultat observé consigné :** Le tableau indique qu'une commande de 6,49 € a pu être passée malgré un minimum de 25 €.
- **Preuve référencée :** `test17.png` dans le CSV ; cette capture n'a pas été retrouvée dans `evidence/` lors de la vérification du dépôt.
- **Sévérité / priorité proposée :** Majeure, P1, si l'observation est reproduite.
- **Cas associé :** TC-BR-05.

**Limite :** vérifier que le minimum de 25 € s'applique bien au restaurant et au parcours testés, et que la commande a réellement été créée. Ajouter la capture réelle avant de considérer la preuve comme jointe.
