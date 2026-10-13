# Stratégie de test — QuickOrder

## 1. Contexte et objectif
QuickOrder est une application web pédagogique de commande de repas développée avec Python, Flask, Flask-SQLAlchemy et SQLite. La mission est d'évaluer sa qualité avant une mise en production simulée. Le code source ne doit pas être modifié pendant la campagne initiale.

Objectifs : comprendre les parcours critiques, prioriser les risques, tester l'interface web et l'API REST, documenter les anomalies avec des preuves, recueillir des retours utilisateurs et proposer des améliorations.

## 2. Périmètre
- Accueil, navigation entre restaurants, recherche, catégories, tri et filtres.
- Consultation d'un restaurant et de ses produits.
- Inscription et connexion avec comptes de démonstration.
- Ajout, modification et suppression d'articles du panier.
- Passage de commande, coupons, adresses et modes de paiement simulés.
- Liste, détail, annulation et renouvellement des commandes.
- Favoris et avis.
- API REST via Swagger : clé d'accès, restaurants, produits, coupons et commandes.
- Validations, statuts HTTP, cohérence des montants, gestion du stock et autorisations.

## 3. Hors périmètre
- Audit complet de l'infrastructure et du réseau.
- Certification juridique ou formelle de sécurité.
- Paiements réels : les paiements sont simulés.
- Tests de charge à grande échelle.
- Modification du code source pendant la campagne initiale.
- Confirmation d'une anomalie sans reproduction ou preuve.

## 4. Environnement et données
- Application : http://127.0.0.1:5000
- Swagger : http://127.0.0.1:5000/docs/
- Clé API de démonstration : quickorder-demo-key.
- Comptes de démonstration : ceux du README et du guide d'installation du dépôt source.
- Système d'exploitation, navigateur, version/commit testé, date et méthode de lancement : à renseigner dans le rapport d'exécution.

Attention : la commande seed.py réinitialise la base locale. Sauvegarder les preuves avant de réinitialiser. Ne pas utiliser de données personnelles réelles.

## 5. Parcours critiques
1. Parcourir les restaurants et trouver un produit.
2. Ajouter un produit disponible au panier et vérifier quantité et total.
3. Passer une commande avec adresse et mode de paiement valide.
4. Vérifier que stock, montant et nombre de commandes restent cohérents.
5. Vérifier que seul le propriétaire ou l'administrateur autorisé peut consulter une commande.
6. Appeler l'API avec une clé valide, puis vérifier le refus d'une clé absente ou invalide.

## 6. Types de tests
- Fonctionnels nominaux : parcours attendus.
- Limites : quantité, stock, montants, champs vides et seuils.
- Négatifs : données mal formées, ID inconnus, clé API invalide.
- Règles métier : stock, panier mono-restaurant, minimum de commande, coupons, paiements et autorisations.
- API : codes HTTP, JSON, validations et cohérence.
- Smoke test : accueil, Swagger et health endpoint.
- Régression : rejouer les cas après correction.
- Exploratoires et utilisateurs : observer les difficultés sans guider les participants.

## 7. Priorisation
La priorité initiale est estimée par Probabilité × Impact, chacun noté de 1 à 3 : 1 faible, 2 moyen, 3 élevé. Score 1–2 : faible ; 3–4 : moyen ; 6 : élevé ; 9 : critique. Il s'agit d'une estimation initiale à réviser après les tests.

Les parcours de commande, montants, stock, doublons et contrôle d'accès sont prioritaires car ils peuvent créer des données incohérentes, des pertes financières simulées ou une atteinte à la confidentialité.

## 8. Critères d'entrée et de sortie
Entrée : application démarrée, pages principales et Swagger accessibles, comptes de démonstration disponibles, environnement consigné.
Sortie : 24 cas avec statut ou raison de blocage, anomalies reproductibles documentées, preuves liées aux cas, statistiques calculées depuis les résultats réels, retours de deux participants minimum, recommandation Go/No-Go justifiée.

## 9. Statuts
- Pass : résultat observé conforme à l'attendu.
- Fail : résultat observé différent de l'attendu, avec preuve et anomalie associée.
- Blocked : dépendance ou environnement empêche le test.
- Skipped : volontairement non exécuté, avec raison.
- À exécuter : campagne non réalisée.

Ne jamais marquer Pass ou Fail sur la seule base de la lecture du code. L'inspection statique oriente les tests ; la confirmation exige une exécution.
