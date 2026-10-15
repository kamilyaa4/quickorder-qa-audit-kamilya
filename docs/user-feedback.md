# Tests utilisateurs — protocole et collecte

## Objectif
Observer si des personnes peuvent accomplir des tâches sur QuickOrder, relever leurs difficultés et proposer des améliorations basées sur des observations.

## Contexte des sessions
Sessions réalisées avec trois camarades de classe, avec leur accord, le 13/10/2026, sur un ordinateur Windows (navigateur : chrome). Environnement de démonstration, comptes de test, aucun paiement réel. Participants anonymes : P1, P2 et P3.

## Scénario U1 — Trouver un restaurant et un produit
Consigne : « Imagine que tu souhaites commander un repas. Trouve un restaurant et ouvre la page d'un produit. »
- P1 : succès (environ 1 minute). Utilise le filtre de catégorie, remarque que tous les restaurants restent affichés, hésite quelques secondes, puis choisit un restaurant.
- P2 : succès (environ 2 minutes). Parcourt la liste sans utiliser le filtre.
- P3 : succès (environ 1 min 30). Utilise le filtre de catégorie, remarque que la liste ne change pas, revient à la liste et choisit un restaurant manuellement.
- Impact : moyen (le filtre ne filtre pas, voir BR-09). Deux participants sur trois ont rencontré le problème en utilisant le filtre.
- Amélioration proposée : corriger le filtre de catégorie.

## Scénario U2 — Ajouter un article et vérifier le panier
Consigne : « Ajoute un produit au panier et vérifie le montant à payer. »
- P1 : succès (environ 1 minute), sans hésitation particulière.
- P2 : succès (environ 2 minutes). Cherche l'accès au panier et parcourt la page avant de le repérer.
- P3 : succès (environ 50 secondes). Repère rapidement l'icône du panier et vérifie que le produit apparaît dans la liste.
- Impact : faible.
- Amélioration proposée : rendre l'accès au panier plus visible.

## Scénario U3 — Explorer la commande et retrouver son suivi
Consigne : « Va aussi loin que possible dans le parcours de commande, puis trouve où consulter une commande. Ne réalise aucun paiement réel. »
- P1 : parcours effectué (environ 3 minutes). Confirme une commande sous le minimum sans aucun message. Cherche ensuite l'accès au suivi de commande.
- P2 : parcours effectué (environ 4 minutes). Hésite sur le champ du montant reçu en espèces, puis la commande est confirmée sans message d'erreur. Cherche ensuite où consulter le suivi.
- P3 : parcours effectué (environ 3 min 30). Remarque qu'aucun avertissement ne s'affiche quand le montant est inférieur au minimum attendu, confirme la commande, puis met quelques instants à trouver où consulter le suivi.
- Impact : élevé (minimum non appliqué et montant en espèces non contrôlé, voir BR-CAND-05 et BR-CAND-06).
- Amélioration proposée : bloquer sous le minimum, contrôler le montant reçu, afficher des messages clairs et rendre le suivi de commande plus facile à trouver.

## Synthèse
| Problème observé | Participants | Fréquence | Impact | Amélioration | Priorité |
|---|---|---|---|---|---|
| Le filtre de catégorie ne change pas la liste | P1, P3 | deux fois | moyen | Corriger le filtre | P2 |
| Le panier n'est pas immédiatement repéré | P2 | une fois | faible | Rendre le panier plus visible | P3 |
| Commande confirmée sous le minimum, sans avertissement | P1, P3 | deux fois | élevé | Bloquer et expliquer le minimum | P1 |
| Montant en espèces insuffisant accepté, champ peu clair | P2 | une fois | élevé | Contrôler et clarifier le champ | P1 |
| Le suivi de commande est difficile à trouver | P1, P2, P3 | trois fois | moyen | Ajouter un lien clair vers Mes commandes | P2 |

## Limites
Trois participants permettent des observations exploratoires, pas une généralisation à tous les utilisateurs. Les participants sont des camarades qui ont travaillé sur le même projet : ils connaissent déjà QuickOrder, ce qui peut atténuer les difficultés que rencontrerait un nouvel utilisateur.
