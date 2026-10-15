# BR-CAND-02 — Produit à stock nul potentiellement visible ou ajoutable

- **Statut :** Observation consignée dans TC-L-02 et TC-BR-02 ; à confirmer avec une preuve accessible.
- **Source à inspecter :** `app/routes/main.py` et `app/routes/shop.py`.
- **Préconditions :** Produit de test avec stock 0 et indicateur disponible.
- **Étapes de reproduction :**
  1. Ouvrir le restaurant.
  2. Rechercher le produit dont le stock est nul.
  3. Tenter de l'ajouter au panier.
  4. Vérifier si la commande peut être confirmée et contrôler le stock avant/après.
- **Résultat attendu :** Un produit en rupture ne devrait pas pouvoir être commandé ; le stock ne doit jamais devenir négatif.
- **Résultat observé consigné :** Le tableau indique qu'un produit en rupture a pu être ajouté au panier.
- **Preuve référencée :** `test7.png` dans le CSV ; cette capture n'a pas été retrouvée dans `evidence/` lors de la vérification du dépôt.
- **Sévérité / priorité proposée :** Majeure, P1, si l'observation est reproduite ; le stock ne devrait pas être contournable.
- **Cas associés :** TC-L-02 et TC-BR-02.

**Limite :** TC-L-02 est intitulé « Quantité égale au stock », mais son résultat obtenu parle d'un produit en rupture. Rejouer le cas avec une quantité exactement égale au stock et séparer ce test de celui portant sur le stock nul. Ne pas présenter la preuve comme jointe tant que le fichier n'est pas ajouté.
