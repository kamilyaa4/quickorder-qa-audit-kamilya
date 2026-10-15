# Rapport d'exécution de la campagne

## Environnement
- Date et heure : 13/10/2026
- Testeur : Kamilya
- Système d'exploitation : Windows
- Navigateur et version : chrome Version 155.0.8059.85
- Version/commit du dépôt source : quickorder-qa-project, branche master, téléchargé le 13/10/2026
- Méthode de lancement (Python ou Docker) : docker compose up --build
- URL : http://127.0.0.1:5000
- Swagger : http://127.0.0.1:5000/docs/
- Docker 27.3.1, Compose v2.30.3

## État initial
## État de la campagne

La campagne a été exécutée en local le 13/10/2026 sur les 24 cas prévus. Les résultats complets et les preuves sont dans test-cases.csv et le dossier evidence.

## Procédure
1. Suivre le guide d'installation du dépôt source.
2. Vérifier que l'accueil et Swagger sont accessibles.
3. Exécuter chaque cas dans test-cases.csv.
4. Remplacer le résultat attendu/observé par l'observation réelle et choisir un statut.
5. Pour chaque Fail, créer un rapport de bug et ajouter une preuve.
6. Recalculer les compteurs depuis les statuts réellement enregistrés.

## Synthèse à compléter
## Synthèse

| Mesure                      | Résultat |
| --------------------------- | -------- |
| Cas prévus                  | 24 |
| Tests exécutés              | 19 |
| Pass                        | 12 |
| Fail                        | 7 |
| Blocked                     | 1 |
| Skipped                     | 4 |
| Taux de réussite            | 50 % des 24 cas (12 sur 19 exécutés, soit 63 %) |
| Anomalies confirmées        | 6 (BR-CAND-02, BR-CAND-05, BR-CAND-06, BR-09, BR-10, BR-11) |
| Anomalies critiques/élevées | 5 majeures (BR-CAND-02, 05, 06, BR-10, BR-11) et 1 moyenne (BR-09) |
## Principaux risques observés

- Stock : un produit en rupture peut être ajouté au panier (TC-L-02, TC-BR-02).
- Montants et paiement : une commande de 6,49 euros passe malgré un minimum de 25 euros (TC-BR-05), et une commande est confirmée avec un montant en espèces insuffisant (TC-BR-06).
- API : une commande sans articles renvoie 201 au lieu de 400 (TC-E-03).
- Règle métier : un produit d'un restaurant fermé peut être ajouté au panier (TC-BR-03).
- Affichage : le filtre par catégorie ne filtre pas (TC-N-01).

Limites : 5 cas n'ont pas pu être exécutés (TC-L-01, TC-L-04, TC-E-02, TC-E-04, TC-E-05), dont le contrôle d'accès aux commandes d'un autre utilisateur. Ces risques restent donc non vérifiés.
## Recommandation Go / No-Go

**No-Go.** Des échecs sont confirmés sur le stock, le montant minimum et le paiement en espèces, ce qui justifie un No-Go jusqu'à correction et re-test, selon la règle de ce rapport.

Conditions pour passer à Go : corriger puis rejouer TC-L-02, TC-BR-02, TC-BR-05, TC-BR-06, TC-E-03, TC-BR-03 et TC-N-01, et exécuter les cas non réalisés, notamment TC-E-05 (contrôle d'accès).

## Re-test
Pour chaque correction, noter le commit, la date, le cas rejoué, le résultat et la preuve. Ne déclarer une correction validée qu'après ré-exécution.
