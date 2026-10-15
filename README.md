# Audit qualité QuickOrder — Kamilya

Projet du cours **Tests et qualité des solutions numériques**. L'objectif est d'évaluer l'application pédagogique QuickOrder, de prioriser les risques, de préparer et exécuter une campagne de tests, de documenter les anomalies et de proposer des améliorations.

## Application auditée
- Dépôt source du professeur : https://github.com/amine-el-amrani/quickorder-qa-project
- Sujet officiel : https://github.com/amine-el-amrani/quickorder-qa-project/blob/master/docs/STUDENT_BRIEF.md
- Installation : https://github.com/amine-el-amrani/quickorder-qa-project/blob/master/docs/INSTALLATION.md
- Interface locale : http://127.0.0.1:5000
- Swagger : http://127.0.0.1:5000/docs/

## Livrables
- [Stratégie de test](docs/test-strategy.md)
- [Matrice des risques](docs/risk-matrix.md)
- [24 cas de test au format Excel](docs/test-cases.xlsx)
- [Version CSV des cas de test](docs/test-cases.csv)
- [Rapport d'exécution](docs/execution-report.md)
- [Suivi des anomalies](docs/bug-reports/README.md)
- [Retours et tests utilisateurs](docs/user-feedback.md)
- [Plan d'amélioration](docs/improvement-plan.md)
- [Guide de collecte des preuves](evidence/README.md)

## État de la campagne
La campagne est datée du 13/10/2026. Le tableau contient 24 cas : 12 Pass, 7 Fail, 1 Blocked et 4 Skipped. Cela correspond à 19 tests exécutés (12 Pass + 7 Fail) et 5 cas non exécutés (1 Blocked + 4 Skipped). Le taux de réussite parmi les tests exécutés est de 63,2 % (12/19).

Les observations de six anomalies sont consignées dans le rapport d'exécution. Les captures référencées dans le CSV (par exemple `test1.png`, `test7.png`) doivent toutefois être ajoutées au dossier `evidence/` : elles ne sont pas actuellement présentes aux chemins référencés. Les anomalies ne doivent être considérées comme entièrement étayées qu'après vérification des preuves et des étapes de reproduction.

**Recommandation actuelle : No-Go**, en raison des écarts observés sur des règles métier importantes. Les cas non exécutés et les preuves manquantes constituent des limites de cette campagne.

## Lancer l'application
Suivre le guide officiel d'installation ci-dessus. Après démarrage, vérifier que l'accueil et Swagger sont accessibles. La clé de démonstration indiquée dans le sujet est `quickorder-demo-key`.

## Méthode
1. Démarrer QuickOrder et noter l'environnement et la date.
2. Exécuter les 24 cas du tableau.
3. Saisir le résultat observé, le statut et une preuve réelle.
4. Reproduire les anomalies avant de les considérer comme confirmées.
5. Faire réaliser les scénarios utilisateurs et consigner les observations réelles.
6. Mettre à jour les statistiques et la recommandation Go/No-Go après la campagne.
