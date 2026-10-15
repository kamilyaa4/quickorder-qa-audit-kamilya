# Suivi des anomalies — QuickOrder

## Règle de statut
Les observations ci-dessous proviennent du tableau de tests et des rapports déjà consignés. Les fichiers de preuve cités (par exemple `test7.png`) ne sont pas actuellement présents dans le dossier `evidence/` aux chemins vérifiés. En conséquence, les éléments ci-dessous sont **des anomalies rapportées à vérifier avec une preuve accessible**, et non des défauts dont la traçabilité est complète. Ne pas présenter une anomalie comme entièrement confirmée tant que les étapes ne sont pas reproductibles et la preuve jointe.

## BR-CAND-01 — Filtre des frais de livraison potentiellement inversé
- Statut : À reproduire.
- Source à inspecter : `app/routes/main.py`, filtre `max_delivery`.
- Préconditions : restaurants avec frais différents.
- Étapes : ouvrir l'accueil, fixer un maximum de frais (ex. 2,50 €), comparer les frais des résultats.
- Attendu : seuls les restaurants dont les frais sont inférieurs ou égaux au maximum sont affichés.
- Observé : non renseigné.
- Preuve : capture et URL avec filtres à ajouter.
- Sévérité/priorité : à confirmer.

## BR-CAND-02 — Produit avec stock nul potentiellement visible et ajoutable
- Statut : Observation rapportée dans TC-L-02 et TC-BR-02 ; preuve à joindre et reproduction à vérifier.
- Source à inspecter : `app/routes/main.py` et `app/routes/shop.py`.
- Préconditions : produit avec stock 0 et disponible dans les données de test.
- Étapes : ouvrir le restaurant, chercher le produit, tenter de l'ajouter au panier.
- Attendu : produit en rupture non commandable.
- Observé consigné : un produit en rupture aurait pu être ajouté au panier. Attention : TC-L-02 est intitulé « Quantité égale au stock », mais son observation concerne un produit en rupture ; rejouer ou corriger ce cas.
- Preuve : `test7.png` est référencé dans le CSV mais le fichier n'a pas été retrouvé dans `evidence/`.
- Sévérité/priorité proposée : majeure, P1, à confirmer après reproduction.

## BR-CAND-03 — Quantité du panier potentiellement supérieure au stock
- Statut : À reproduire.
- Source à inspecter : `app/routes/shop.py`.
- Préconditions : stock connu.
- Étapes : ajouter le produit, modifier la quantité au-delà du stock, tenter de confirmer.
- Attendu : quantité refusée ou limitée au stock ; stock jamais négatif.
- Observé : non renseigné.
- Preuve : panier et stock avant/après à ajouter.
- Sévérité/priorité : à confirmer.

## BR-CAND-04 — Confirmation PayPal pouvant créer deux commandes
- Statut : À reproduire.
- Source à inspecter : `app/routes/orders.py` et `app/routes/api.py`.
- Préconditions : panier valide dans un environnement réinitialisable.
- Étapes : noter le nombre de commandes, confirmer une seule fois avec PayPal simulé, recompter les commandes et vérifier le stock.
- Attendu : une seule confirmation crée une seule commande.
- Observé : non renseigné.
- Preuve : commandes et stock avant/après à ajouter.
- Sévérité/priorité : potentiellement critique si reproduit.

## BR-CAND-05 — Minimum de commande potentiellement non appliqué au checkout
- Statut : Observation rapportée dans TC-BR-05 ; preuve à joindre et reproduction à vérifier.
- Source à inspecter : `app/routes/orders.py`.
- Préconditions : minimum supérieur au sous-total.
- Étapes : composer un panier inférieur au minimum, ouvrir checkout et tenter de confirmer.
- Attendu : confirmation bloquée et minimum expliqué.
- Observé consigné : une commande à 6,49 € aurait été passée alors que le minimum indiqué était de 25 €.
- Preuve : `test17.png` est référencé dans le CSV mais le fichier n'a pas été retrouvé dans `evidence/`.
- Sévérité/priorité proposée : majeure, P1, à confirmer après reproduction.

## BR-CAND-06 — Paiement espèces potentiellement accepté si montant insuffisant
- Statut : Observation rapportée dans TC-BR-06 ; preuve à joindre et reproduction à vérifier.
- Source à inspecter : `app/routes/orders.py`.
- Préconditions : panier valide et paiement espèces disponible.
- Étapes : relever le total, saisir un montant reçu inférieur, confirmer et vérifier l'état de la commande.
- Attendu : commande non confirmée si montant insuffisant.
- Observé consigné : la commande aurait été confirmée malgré un montant reçu inférieur au total.
- Preuve : `test18.png` est référencé dans le CSV mais le fichier n'a pas été retrouvé dans `evidence/`.
- Sévérité/priorité proposée : majeure, P1, à confirmer après reproduction.

## BR-CAND-07 — API susceptible d'ignorer le stock
- Statut : À reproduire.
- Source à inspecter : `app/routes/api.py`, `POST /orders`.
- Préconditions : clé API valide et produit avec stock connu.
- Étapes : envoyer une commande dont la quantité dépasse le stock, vérifier le statut HTTP, le JSON et le stock.
- Attendu : requête refusée, stock jamais négatif.
- Observé : non renseigné.
- Preuve : requête/réponse et stock avant/après à ajouter.
- Sévérité/priorité : potentiellement critique si reproduit.

## BR-CAND-08 — Recherche d'accueil pouvant ignorer la description du restaurant
- Statut : Hypothèse à clarifier, non confirmée.
- Source à inspecter : `app/routes/main.py`.
- Préconditions : terme présent dans la description mais absent du nom d'un restaurant.
- Étapes : rechercher le terme et vérifier si le restaurant apparaît.
- Attendu : à définir selon les exigences produit ; sans exigence claire, ne pas déclarer un bug.
- Observé : non renseigné.
- Preuve : capture de la recherche et description du restaurant à ajouter.
- Sévérité/priorité : à confirmer.

## Anomalies supplémentaires rapportées dans le tableau de tests

### BR-09 — Le filtre par catégorie ne filtre pas
- Statut : Observation rapportée dans TC-N-01 ; preuve à joindre et reproduction à vérifier.
- Attendu : seuls les restaurants de la catégorie sélectionnée apparaissent.
- Observé consigné : tous les restaurants resteraient affichés.
- Preuve : `test 1.png` est référencé dans le CSV mais n'a pas été retrouvé dans `evidence/`.
- Sévérité/priorité proposée : moyenne, P2, à confirmer.

### BR-10 — L'API accepte une commande sans articles
- Statut : Observation rapportée dans TC-E-03 ; preuve à joindre et reproduction à vérifier.
- Étapes : envoyer `POST /orders` avec un tableau `items` vide.
- Attendu : réponse de validation (le cas de test attend HTTP 400).
- Observé consigné : réponse HTTP 201.
- Preuve : `test12.png` est référencé dans le CSV mais n'a pas été retrouvé dans `evidence/`.
- Sévérité/priorité proposée : majeure, P2, à confirmer.

### BR-11 — Un produit d'un restaurant fermé peut être ajouté au panier
- Statut : Observation rapportée dans TC-BR-03 ; preuve à joindre et reproduction à vérifier.
- Attendu : la commande doit être refusée si le restaurant est fermé. L'ajout au panier seul ne prouve pas que la commande finale est acceptée.
- Observé consigné : un produit d'un restaurant fermé aurait pu être ajouté au panier.
- Preuve : `test15.png` est référencé dans le CSV mais n'a pas été retrouvé dans `evidence/`.
- Sévérité/priorité proposée : majeure, P2, à confirmer après test du parcours de commande complet.

## Modèle pour toute anomalie
- ID et titre :
- Statut : Confirmé / Non reproduit / En attente de preuve
- Date et environnement :
- Préconditions :
- Étapes exactes :
- Résultat attendu :
- Résultat observé :
- Preuve réelle jointe :
- Sévérité : Bloquante / Majeure / Moyenne / Mineure
- Priorité : P1 / P2 / P3
- Cas de test associé :
- Correction et re-test :
