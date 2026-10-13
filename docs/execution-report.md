# Rapport d'exécution de la campagne

## Environnement
- Date et heure : 13/10/2026
- Testeur : Kamilya
- Système d'exploitation : Windows
- Navigateur et version : Docker 27.3.1, Compose v2.30.3
- Version/commit du dépôt source : à renseigner
- Méthode de lancement (Python ou Docker) : docker compose up --build
- URL : http://127.0.0.1:5000
- Swagger : http://127.0.0.1:5000/docs/

## État initial
**La campagne n'a pas encore été exécutée dans un environnement local.** Les 24 cas sont préparés ; les résultats doivent être collectés réellement.

| Indicateur | Valeur actuelle |
|---|---:|
| Cas prévus | 24 |
| Pass | À calculer |
| Fail | À calculer |
| Blocked | À calculer |
| Skipped | À calculer |
| Non exécutés au départ | 24 |

## Procédure
1. Suivre le guide d'installation du dépôt source.
2. Vérifier que l'accueil et Swagger sont accessibles.
3. Exécuter chaque cas dans test-cases.csv.
4. Remplacer le résultat attendu/observé par l'observation réelle et choisir un statut.
5. Pour chaque Fail, créer un rapport de bug et ajouter une preuve.
6. Recalculer les compteurs depuis les statuts réellement enregistrés.

## Synthèse à compléter
| Mesure | Résultat |
|---|---|
| Tests exécutés | À compléter |
| Pass | À compléter |
| Fail | À compléter |
| Blocked | À compléter |
| Skipped | À compléter |
| Taux de réussite | À calculer seulement si des tests ont été exécutés |
| Anomalies confirmées | À compléter |
| Anomalies critiques/élevées | À compléter |

## Principaux risques observés
À compléter uniquement depuis les tests réellement exécutés et les preuves. Les pistes issues de la lecture du code ne sont pas des anomalies confirmées.

## Recommandation Go / No-Go
**Décision en attente.** La recommandation sera justifiée après exécution des tests critiques. Un échec confirmé sur stock, paiement, montant, doublon ou contrôle d'accès justifie un No-Go jusqu'à correction et re-test.

## Re-test
Pour chaque correction, noter le commit, la date, le cas rejoué, le résultat et la preuve. Ne déclarer une correction validée qu'après ré-exécution.
