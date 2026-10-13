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
- Statut : À reproduire.
- Source : app/routes/main.py et app/routes/shop.py.
- Préconditions : produit stock 0 et disponible dans les données de test.
- Étapes : ouvrir le restaurant, chercher le produit, tenter de l'ajouter au panier.
- Attendu : produit en rupture non commandable.
- Observé : à renseigner. Preuve : menu, panier et stock avant/après.
- Sévérité/priorité : à confirmer.

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
- Statut : À reproduire.
- Source : app/routes/orders.py.
- Préconditions : minimum supérieur au sous-total.
- Étapes : composer un panier inférieur au minimum, ouvrir checkout et tenter de confirmer.
- Attendu : confirmation bloquée et minimum expliqué.
- Observé : à renseigner. Preuve : checkout et résultat de commande.
- Sévérité/priorité : à confirmer.

## BR-CAND-06 — Paiement espèces potentiellement accepté si montant insuffisant
- Statut : À reproduire.
- Source : app/routes/orders.py.
- Préconditions : panier valide et paiement espèces disponible.
- Étapes : relever le total, saisir un montant reçu inférieur, confirmer et vérifier l'état de la commande.
- Attendu : commande non confirmée si montant insuffisant.
- Observé : à renseigner. Preuve : formulaire et détail de commande.
- Sévérité/priorité : potentiellement élevée si reproduit.

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
