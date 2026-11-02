# Roadmap de livraison — MonEglise MVP

**Objectif :** une expérience utilisable de prière participative avant le lancement de fonctionnalités financières. Dates non engagées ; réévaluer à chaque revue Produit.

| Phase | Périmètre | Livrable / preuve | Gate |
|---|---|---|---|
| **0. Fondation** | Flutter + Go, auth, stockage privé, CI, permissions, modération minimale | staging et parcours connexion contrôlé | revues code/sécurité |
| **1. Prayer MVP** | intentions texte, fil, réaction « Je prie », réponse texte/audio, lecture autorisée | deux utilisateurs peuvent s'envoyer une prière vocale authentique | test vie privée + modération |
| **2. Communautés** | communauté ouverte, Églises vérifiées, rattachement facultatif, intentions communautaires | pilote catholique + protestant + sans Église | isolation et consentement |
| **3. Amens** | achats, transferts, dons et règlements via partenaires | sandbox et scénario comptable réconcilié ; production conditionnelle | **juridique + finance + stores** |
| **4. Vie des Églises** | annonces audio/SMS, projets, contribution volontaire | pilote institutionnel | consentement, délivrabilité, suivi |

## Backlog recommandé P0
1. Identité et sessions sécurisées.
2. Publications d'intentions avec états, visibilité, file de modération.
3. Participation gratuite à la prière.
4. Réponses texte et vocale avec lecture protégée.
5. Signalement, suspension et audit des interventions.
6. CI automatisée, tests d'autorisation, observabilité et sauvegarde.

## Critères d'acceptation généraux
- Tous les endpoints sensibles ont des contrôles autorisation/visibilité côté serveur.
- Audio non accessible sans autorisation même si l'URL ou l'identifiant est connu.
- Comportement correct en réseau mobile intermittent.
- Absence de blocage payant de la prière et d'affiliation forcée.
- Bugs de confidentialité, de paiement ou de double dépense considérés bloquants.

## Mesures pilotes
Pourcentage d'intentions recevant une prière, délai de première réponse, taux d'écoute audio, rétention hebdomadaire, satisfaction, signalements et délai de modération. Ne pas utiliser les dons comme unique indicateur de succès.

## Hors périmètre à ce stade
ERP d'Église, gestion financière paroissiale complète, sacrements, classement d'utilisateurs, publicité comportementale, intercessions payantes, IA générant automatiquement de « vraies » prières attribuées à des personnes.
