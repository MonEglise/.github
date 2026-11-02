# MonEglise — Sécurité, confidentialité et Trust & Safety

**Nature :** principes publics ; ne jamais publier ici les inventaires de production, clés, topologies réelles, chemins d'administration, journaux d'incidents ni données d'utilisateurs.

## Risques de premier ordre
Les intentions et les prières peuvent révéler convictions religieuses, santé, difficultés personnelles, informations sur des proches et voix d'utilisateurs. Protéger leurs auteurs et leurs destinataires est une exigence produit fondamentale.

## Contrôles indispensables
1. **Minimisation** : demander le minimum nécessaire ; pas d'exposition par défaut, possibilité d'alias.
2. **Confidentialité** : public / communauté / privé selon politiques réelles, et contrôle d'autorisation serveur pour chaque lecture, recherche et notification.
3. **Audio** : stockage chiffré privé, URLs expirantes, contrôles sur le destinataire, maîtrise de conservation, suppression et révocation d'accès.
4. **Authentification** : OTP rate-limited, sessions révocables, protection contre l'énumération et les accès automatisés.
5. **Modération** : signalement, blocage, examen humain, gestion des appels, mécanismes anti-harcèlement et anti-fraude.
6. **Protection des vulnérables** : pas de vente de guérison, pas de promesse spirituelle marchande, parcours de soutien adaptés aux situations de crise et aux mineurs.
7. **Journal d'audit** : noter les actes d'administration sensibles, sans copier le contenu de prière dans les logs.
8. **Fournisseurs** : contrats de traitement des données, contrôle des transferts internationaux, restrictions de conservation.
9. **Maintenance** : dépendances surveillées, pentests ciblés, réponse aux incidents, restauration testée.
10. **Droits des utilisateurs** : accès, rectification, suppression et traitement des demandes selon le droit applicable.

## Gates de livraison
- Toute nouvelle fonctionnalité doit inclure son **threat model** : actifs, auteurs, abus, contrôles, journalisation.
- Tester les cas **IDOR/BOLA** (accès à l'intention d'un autre, média d'une autre communauté), replay de jeton, upload malveillant et exfiltration.
- Vérifier les permissions de lecture même pour les notifications et URLs de lecture audio.
- Appliquer le principe du moindre privilège, notamment à la modération et à la prise en charge support.
- Interdire les données personnelles réelles dans les fixtures, traces et environnements de développement.

## Paiements et Amens
Toute transition du mode sandbox à un transfert de valeur réel requiert :
- validation juridique et partenaire habilité ;
- ledger à double entrée et rapprochement de bout en bout ;
- webhook vérifié/idempotent ;
- contrôles fraude, limites, remboursements et règlement des Églises ;
- revue de sécurité indépendante.

## Incidents
Ne jamais ajouter d'identifiants, d'IP de serveurs, de secrets ou de preuves non caviardées dans des issues publiques. Rapporter les vulnérabilités par canal privé défini dans [SECURITY.md](../SECURITY.md), en utilisant l'option privée GitHub Security Advisories si disponible.
