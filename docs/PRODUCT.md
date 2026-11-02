# MonEglise — Product brief (MVP)

**Statut :** cadrage fonctionnel, non validation de mise en production. **Dernière mise à jour :** 2026-11-02.
**Sponsor :** GENIUS GROUPS SAS. **Produit :** MonEglise. **Devise produit :** « Vous rapprocher de l’Église et de Dieu. »

## 1. Pourquoi MonEglise ?

MonEglise **n'est pas** un logiciel de gestion d'Église (membership/ERP), ni un réseau social généraliste. C'est un produit de **prière participative** : confier une intention, prier pour quelqu'un, recevoir et écouter des prières, puis soutenir sa communauté.

### Trois piliers
1. **Prière :** intention publiée, engagement « Je prie », réponse texte/audio, écoute sécurisée.
2. **Fraternité :** prière pour autrui et Amens de soutien (fonctionnalité financière conditionnelle).
3. **Communauté :** affiliation facultative à une ou plusieurs Églises, intentions communautaires, contributions (progressives et réglementées).

### Principes invariants
- **La prière est gratuite et ne peut pas être conditionnée à un paiement.**
- Un fidèle **sans Église** peut s'inscrire, publier et prier dans la communauté ouverte.
- Respect de différentes traditions chrétiennes ; **aucune autorité doctrinale centrale** exercée par le logiciel.
- La priorité du flux est **l'intention et la prière**, non le don et non une métrique de popularité.
- Données sensibles : consentement, choix de visibilité, modération, suppression et accès contrôlé.
- « Je prie » ne doit pas être confondu avec une prière effectivement enregistrée ou une garantie de résultat.

## 2. Acteurs
| Rôle | Capacité initiale |
|---|---|
| Visiteur | Comprendre le produit et consulter les informations publiques explicitement ouvertes |
| Fidèle | Authentification, intention, réaction, prière texte/vocale, notifications consenties |
| Modérateur | Examiner signalements et contenus, restreindre les abus, tracer les décisions |
| Responsable d'Église vérifiée | Gérer l'espace communautaire et ses communications dans le périmètre autorisé |
| Opérations | Administration technique limitée, audit et suivi des incidents |
| Partenaire financier | Traitement monétaire, conformité et règlement selon mandat vérifié |

Les rôles d'Église sont **scopés par communauté** ; être responsable de A n'autorise aucun accès à B.

## 3. Parcours de référence (P0)

**Parcours A — Publier :** compte → intention texte → choisir public / communauté / privé (selon politique de diffusion) → vérification/modération → publication → suivi des réponses.

**Parcours B — Répondre :** découvrir l'intention autorisée → « Je prie » (facultatif) → réponse texte ou enregistrement vocal → confirmation → notification au destinataire autorisé → écoute.

**Parcours C — Sécurité :** signaler une intention ou une prière → file de modération → décision explicite → recours/support → événement d'audit.

**Parcours D — Communautés (P1 produit) :** rechercher une Église vérifiée → suivre/rejoindre avec son accord → consulter son flux d'intentions ; l'affiliation demeure facultative.

## 4. Règles métier initiales
- Expérimenter **5 intentions mises en avant par jour et par communauté**, pas 5 intentions globales pour l'ensemble du produit ; gouvernance de la file d'attente. **Ce n'est pas une limite de 5 prières par utilisateur.**
- Une intention a `visibility`, `status`, `author_id`, `community_id?`, `created_at` et `published_at?`; pas de contenu rendu visible avant autorisation.
- Respecter les utilisateurs bloqués et les permissions de communautés **dans la requête API et l'accès média**.
- Les prières vocales ne doivent pas être enregistrées ou rendues publiques par défaut ; identité et distribution de l'audio selon choix de confidentialité.
- Pour les notifications, limiter la fréquence et donner le contrôle au destinataire ; aucune gamification incitant aux contenus sensibles.

## 5. Non-objectifs du MVP
Pas de gestion de paie, comptabilité paroissiale, registre des sacrements, ERP d'Église, messagerie illimitée, marketing publicitaire ciblant les croyances, live-streaming, fonctionnalités IA pastorales autonomes, classements publics de donateurs ni promesses de guérison.

## 6. Critères de validation du pilote
- Une intention reçoit et peut lire/écouter des réponses authentiques de manière sécurisée.
- Mesurer le délai jusqu'à la première prière, le taux d'intentions accompagnées, la lecture/écoute des réponses, le retour hebdomadaire, les incidents et la qualité de modération.
- Réaliser des tests avec des fidèles **avec et sans Église**, et plusieurs traditions chrétiennes.
- Aucun parcours « Amen payant » en production tant que le jalon conformité du document [AMENS.md](AMENS.md) n'est pas validé.

## 7. Source de vérité
Cette note décrit le **périmètre approuvé pour la conception**, pas une promesse de livraison. Tout changement impactant la gratuité de la prière, la confidentialité, la valeur des Amens, les versements ou la conformité exige une décision explicite de la Direction produit et des responsables compétents.
