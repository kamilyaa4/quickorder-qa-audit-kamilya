# Suivi des anomalies — QuickOrder

## Statut des éléments ci-dessous
Les huit pistes sont issues de commentaires présents dans le code source public. Elles sont des **candidats à reproduire**, pas huit bugs déjà confirmés par exécution. Avant de les présenter comme anomalies confirmées, lancer l'application, suivre les étapes et joindre une preuve. Si une piste ne se reproduit pas, consigner le résultat.

## BR-CAND-01 — Filtre de frais de livraison potentiellement inversé
- Statut : À reproduire.
- Source à inspecter : app/routes/main.py, filtre max_delivery.
- Préconditions : restaurants avec frais différents.
- Étapes : ouvrir l'accueil, fixer un maximum de frais (ex. 2,50 €), comparer les frais des résultats.
- Attendu : seuls les restaurants dont les frais sont inférieurs ou égaux au maximum sont affichés.
- Observé : à renseigner. Preuve : capture et URL avec filtres.
- Sévérité/priorité : à confirmer.

## BR-CAND-02 — Produit avec stock nul potentiellement visible et ajoutable
- Statut : Confirmé.
- Source : app/routes/main.py et app/routes/shop.py.
- Préconditions : produit stock 0 et disponible dans les données de test.
- Étapes : ouvrir le restaurant, chercher le produit, tenter de l'ajouter au panier.
- Attendu : produit en rupture non commandable.
- Observé : un produit en rupture de stock peut être ajouté au panier (TC-L-02 et TC-BR-02. Preuve : test7.png.
- Sévérité/priorité : Majeure, P1 (le stock ne doit pas être contournable).

## BR-CAND-03 — Quantité du panier non plafonnée au stock
- Statut : À reproduire.
- Source : app/routes/shop.py, modification du panier.
- Préconditions : stock connu.
- Étapes : ajouter le produit, modifier la quantité au-delà du stock, tenter de confirmer.
- Attendu : quantité refusée ou limitée au stock.
- Observé : à renseigner. Preuve : panier et stock avant/après.
- Sévérité/priorité : à confirmer.

## BR-CAND-04 — Confirmation PayPal pouvant créer deux commandes
- Statut : À reproduire.
- Source : app/routes/orders.py et app/routes/api.py.
- Préconditions : panier valide et environnement réinitialisable.
- Étapes : noter le nombre de commandes, confirmer une seule fois avec PayPal simulé, recompter les commandes et vérifier le stock.
- Attendu : une seule commande pour une seule confirmation.
- Observé : à renseigner. Preuve : commandes et stock avant/après.
- Sévérité/priorité : potentiellement critique si reproduit.

## BR-CAND-05 — Minimum de commande potentiellement non appliqué au checkout
- Statut : Confirmé.
- Source : app/routes/orders.py.
- Préconditions : minimum supérieur au sous-total.
- Étapes : composer un panier inférieur au minimum, ouvrir checkout et tenter de confirmer.
- Attendu : confirmation bloquée et minimum expliqué.
- Observé :le minimum de commande est de 25 euros, mais une commande à 6,49 euros a pu être passée (TC-BR-05). Preuve : test17.png.
- Sévérité/priorité : Majeure, P1 (règle métier non appliquée)..

## BR-CAND-06 — Paiement espèces potentiellement accepté si montant insuffisant
- Statut : Confirmé.
- Source : app/routes/orders.py.
- Préconditions : panier valide et paiement espèces disponible.
- Étapes : relever le total, saisir un montant reçu inférieur, confirmer et vérifier l'état de la commande.
- Attendu : commande non confirmée si montant insuffisant.
- Observé : la commande est confirmée alors que le montant reçu en espèces est inférieur au total (TC-BR-06). Preuve : test18.png.
- Sévérité/priorité : Majeure, P1 (incohérence de paiement).

## BR-CAND-07 — API susceptible d'ignorer le stock
- Statut : À reproduire.
- Source : app/routes/api.py, POST /orders.
- Préconditions : clé API valide et produit avec stock connu.
- Étapes : envoyer une commande dont la quantité dépasse le stock, vérifier le statut HTTP, le JSON et le stock.
- Attendu : requête refusée, stock jamais négatif.
- Observé : à renseigner. Preuve : requête/réponse et stock avant/après.
- Sévérité/priorité : potentiellement critique si reproduit.

## BR-CAND-08 — Recherche d'accueil portant potentiellement seulement sur le nom
- Statut : À reproduire.
- Source : app/routes/main.py.
- Préconditions : terme présent dans la description d'un restaurant mais absent de son nom.
- Étapes : rechercher ce terme et vérifier si le restaurant apparaît.
- Attendu : à préciser selon le comportement produit attendu ; clarifier le besoin avant de déclarer un bug.
- Observé : à renseigner. Preuve : recherche et description.
- Sévérité/priorité : à confirmer.

## Modèle pour toute anomalie confirmée
- ID et titre :
- Statut : Confirmé / Non reproduit / En attente
- Date et environnement :
- Préconditions :
- Étapes exactes :
- Résultat attendu :
- Résultat observé :
- Preuve :
- Sévérité : Bloquante / Majeure / Moyenne / Mineure
- Priorité : P1 / P2 / P3
- Cas de test associé :
- Correction et re-test :


## Anomalies confirmées en plus des pistes

## BR-09 — Le filtre par catégorie ne filtre pas

- Statut : Confirmé.
- Date et environnement : 13/10/2026, Windows, Docker, http://127.0.0.1:5000.
- Étapes : ouvrir l'accueil, puis sélectionner une catégorie.
- Attendu : seuls les restaurants de la catégorie apparaissent.
- Observé : tous les restaurants restent affichés.
- Preuve : test1.png.
- Sévérité/priorité : Moyenne, P2.
- Cas de test associé : TC-N-01.

## BR-10 — L'API accepte une commande sans articles

- Statut : Confirmé.
- Date et environnement : 13/10/2026, Swagger, clé quickorder-demo-key.
- Étapes : POST /orders avec un tableau items vide.
- Attendu : l'API retourne 400 avec un message explicite.
- Observé : l'API retourne 201.
- Preuve : test12.png.
- Sévérité/priorité : Majeure, P2.
- Cas de test associé : TC-E-03.

## BR-11 — Un produit d'un restaurant fermé peut être ajouté au panier

- Statut : Confirmé.
- Date et environnement : 13/10/2026, Windows, Docker, http://127.0.0.1:5000.
- Étapes : ajouter un produit d'un restaurant fermé, puis tenter la commande.
- Attendu : la commande est refusée quand le restaurant est fermé.
- Observé : on peut ajouter un produit d'un restaurant fermé.
- Preuve : test15.png.
- Sévérité/priorité : Majeure, P2.
- Cas de test associé : TC-BR-03.
