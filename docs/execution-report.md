# Rapport d'exécution de la campagne

## Environnement
- Date déclarée de la campagne : 13/10/2026
- Testeur : Kamilya
- Système d'exploitation : Windows
- Navigateur déclaré : Chrome 155.0.8059.85
- Version/commit du dépôt source : quickorder-qa-project, branche master, téléchargé le 13/10/2026
- Méthode de lancement déclarée : `docker compose up --build`
- URL déclarée : http://127.0.0.1:5000
- Swagger : http://127.0.0.1:5000/docs/
- Docker 27.3.1 ; Docker Compose v2.30.3

## État de la campagne
Le tableau `docs/test-cases.csv` contient 24 cas. Les statuts consignés donnent 12 Pass, 7 Fail, 1 Blocked et 4 Skipped.

| Mesure | Résultat |
|---|---:|
| Cas prévus | 24 |
| Tests exécutés (Pass + Fail) | 19 |
| Pass | 12 |
| Fail | 7 |
| Blocked | 1 |
| Skipped | 4 |
| Cas non exécutés (Blocked + Skipped) | 5 |
| Taux de réussite parmi les tests exécutés | 63,2 % (12/19) |
| Taux de réussite sur l'ensemble des cas prévus | 50 % (12/24) |

Les pourcentages répondent à deux questions différentes : 63,2 % des tests exécutés sont Pass ; 50 % des cas prévus sont Pass. Les cas bloqués et ignorés ne sont pas comptés comme des tests réussis.

## Principales observations consignées
- **TC-N-01 — Filtre de catégorie :** le résultat obtenu indique que la liste ne change pas après sélection d'une catégorie.
- **TC-L-02 et TC-BR-02 — Stock nul :** le résultat obtenu indique qu'un produit en rupture a pu être ajouté au panier. Attention : le titre de TC-L-02 porte sur une quantité égale au stock, alors que son observation parle d'un produit en rupture ; ce cas doit être rejoué ou reformulé pour que l'attendu et l'observé correspondent.
- **TC-E-03 — Commande API sans articles :** le tableau indique une réponse 201 alors que le test attend une réponse 400.
- **TC-BR-03 — Restaurant fermé :** le résultat obtenu indique qu'un produit d'un restaurant fermé peut être ajouté au panier. Il faut distinguer l'ajout au panier de l'acceptation finale de la commande.
- **TC-BR-05 — Minimum de commande :** le tableau indique qu'une commande de 6,49 € a été passée alors que le minimum indiqué est 25 €.
- **TC-BR-06 — Paiement espèces :** le tableau indique que la commande a été confirmée malgré un montant reçu insuffisant.

Ces observations sont celles consignées dans le tableau de tests. Les fichiers de preuve mentionnés dans la colonne « Preuve » ne sont pas actuellement présents dans le dossier `evidence/` aux chemins vérifiés. Il faut ajouter les captures réelles ou corriger les références avant de présenter les preuves comme jointes au dépôt.

## Cas non exécutés
- TC-L-01 : bloqué, car une session était déjà connectée.
- TC-L-04 : ignoré, consigne non comprise.
- TC-E-02 : ignoré, consigne non comprise.
- TC-E-04 : ignoré, consigne non comprise.
- TC-E-05 : ignoré, consigne non comprise.

Le contrôle d'accès aux commandes d'un autre utilisateur (TC-E-05) reste donc non vérifié.

## Anomalies et limites
Les observations de TC-N-01, TC-E-03, TC-BR-03, TC-BR-05 et TC-BR-06, ainsi que l'observation sur le stock, sont consignées dans le tableau et dans les rapports d'anomalies. Pour une traçabilité complète, chaque anomalie doit avoir des étapes reproductibles, un résultat attendu, un résultat observé et une preuve réelle accessible. Les références de captures inscrites dans le CSV ne sont pas encore retrouvées dans `evidence/` ; cette limite doit être résolue avant de prétendre que les preuves sont jointes.

## Recommandation Go / No-Go
**No-Go à titre de recommandation provisoire.** Les observations consignées concernent des règles métier importantes : stock, minimum de commande, paiement et commandes API. La recommandation devra être réévaluée après confirmation reproductible, ajout des preuves, correction éventuelle et re-test.

Conditions avant de reconsidérer un Go :
1. Reproduire les anomalies et joindre les preuves réelles.
2. Corriger les incohérences entre intitulés, résultats observés et statuts.
3. Exécuter les cinq cas non exécutés, notamment TC-E-05 (contrôle d'accès).
4. Rejouer les tests concernés après correction et effectuer les tests de régression pertinents.

## Re-test
Pour chaque correction, noter la version/commit, la date, le cas rejoué, le résultat et la preuve. Ne déclarer une correction validée qu'après ré-exécution.
