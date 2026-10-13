# Audit qualité QuickOrder — Kamilya

Projet du cours **Tests et qualité des solutions numériques**. L'objectif est d'évaluer l'application pédagogique QuickOrder, de prioriser les risques, de préparer et exécuter une campagne de tests, de documenter les anomalies avec des preuves et de proposer des améliorations.

## Application auditée
- Dépôt source du professeur : https://github.com/amine-el-amrani/quickorder-qa-project
- Sujet officiel : https://github.com/amine-el-amrani/quickorder-qa-project/blob/master/docs/STUDENT_BRIEF.md
- Installation : https://github.com/amine-el-amrani/quickorder-qa-project/blob/master/docs/INSTALLATION.md
- Interface locale : http://127.0.0.1:5000
- Swagger : http://127.0.0.1:5000/docs/

## Livrables
- [Stratégie de test](docs/test-strategy.md)
- [Matrice des risques](docs/risk-matrix.md)
- [24 cas de test au format CSV, ouvrable dans Excel](docs/test-cases.csv)
- [Rapport d'exécution](docs/execution-report.md)
- [Pistes de bugs à reproduire](docs/bug-reports/README.md)
- [Protocole de tests utilisateurs](docs/user-feedback.md)
- [Plan d'amélioration](docs/improvement-plan.md)
- [Guide de collecte des preuves](evidence/README.md)

## État d'avancement
Les livrables de préparation sont déposés. La campagne d'exécution, les preuves, les anomalies confirmées et les retours utilisateurs restent à collecter après lancement de l'application. Aucun résultat de test ni témoignage n'est inventé. Les pistes de bugs identifiées par inspection du code doivent être reproduites avant d'être déclarées confirmées.

## Lancer l'application
Suivre le guide officiel d'installation ci-dessus. Après démarrage, vérifier l'accueil et Swagger. La clé API de démonstration indiquée dans le sujet est `quickorder-demo-key`.

## Méthode
1. Démarrer QuickOrder et noter l'environnement et la date.
2. Exécuter les 24 cas du CSV.
3. Saisir le résultat observé, le statut et une preuve.
4. Reproduire les pistes de bugs avant de les confirmer.
5. Faire réaliser les scénarios par au moins deux personnes et consigner leurs retours réels.
6. Mettre à jour les statistiques et la recommandation Go/No-Go après la campagne.
