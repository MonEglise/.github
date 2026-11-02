# MonEglise — Architecture de référence (Flutter + Go)

**Statut :** architecture cible proposée / MVP. Les environnements et domaines de production sont à définir dans un dépôt **privé** dédié.

## 1. Topologie

```text
Flutter Android/iOS
      │ HTTPS (auth, API REST /v1)
      ▼
Go API (monolithe modulaire)
      ├─ identity, users, communities
      ├─ intentions, prayers, media, moderation
      ├─ notifications, audit
      └─ amens / payments / settlements [feature flag, OFF avant validation]
      │             │               │
      ▼             ▼               ▼
 PostgreSQL    Object storage      Queue/outbox
 (migrations)   privé (audio)      + Go worker
      │
    Redis (quota, cache / rate limit ; jamais source comptable)
```

## 2. Frontend
- Flutter et Dart, Android/iOS. Organisation **feature-first**, présentation / domaine / data clairement séparés.
- Navigation `go_router`, état `Riverpod`, HTTP `Dio` : propositions à confirmer par l'équipe technique avant gel.
- Aucun secret, rôle privilégié, valeur d'Amen ou autorisation calculés comme source de vérité côté client.
- Gestion réseau intermittent, feedback d'erreur compréhensible, audio compressé, accessibilité de la lecture, respect de l'économie de données mobiles.
- Tester les transitions permission microphone refusée → réponse texte, perte réseau → reprise, audio non autorisé → refus.

## 3. Backend
- Go monolithe modulaire ; API et worker sont deux exécutables partageant des packages internes versionnés.
- Transport HTTP avec `net/http` ou routeur léger, `pgx` + `sqlc` recommandé, migrations versionnées.
- Contrats OpenAPI, validation des données d'entrée, authN/authZ par ressource, erreurs structurées, pagination à curseur.
- Toujours utiliser `context.Context`, transactions bornées, deadlines réseau, limites de taille pour upload et réponse.
- Idempotence obligatoire sur les opérations qui peuvent créer une valeur, modifier un solde ou enregistrer un événement répété.

## 4. Audio et confidentialité
1. Le client demande une autorisation d'upload temporaire (objet isolé par identifiant opaque).
2. Le service vérifie droits, mime/type/taille/durée attendus et quotas.
3. L'audio est stocké dans un bucket **privé**, et subit les contrôles de sécurité/modération nécessaires avant publication.
4. Toute lecture demande une nouvelle autorisation serveur liée à l'intention et au destinataire ; accès via URL courte durée ou proxy autorisé.
5. Retirer l'accès à l'audio si contenu ou compte est supprimé ou modéré ; appliquer les politiques de conservation définies.

Ne jamais exposer de bucket en lecture publique, ni inclure de lien permanent dans des notifications.

## 5. Modèle de données (vue conceptuelle)
- `users, profiles, auth_sessions`
- `communities, community_members, community_roles`
- `prayer_intentions, prayer_participations, prayer_responses`
- `media_assets, reports, moderation_actions`
- `notification_outbox, audit_events`
- **Préparé mais désactivé :** `amen_accounts, amen_postings, payment_orders, payment_events, church_settlements`

Toute migration doit définir contraintes, index, principes de suppression et tests de retour arrière. Préserver l'historique requis pour la comptabilité sans conserver indûment les contenus de prière.

## 6. Isolation, gestion des droits et identité
- `community_id` scoping appliqué dans les services et requêtes autorisées, jamais uniquement dans les vues.
- ACL explicites pour les objets publics / communauté / privés ; la communauté ouverte n'implique pas un accès public illimité.
- Séparer identités individuelles et rôles institutionnels ; vérification avant tout accès « responsable d'Église ».
- Aucun accès transversal aux données privées par défaut, y compris pour le support.

## 7. Qualité et exploitation
- Tests unitaires des règles métier, intégration PostgreSQL, contrats API, tests Flutter, tests end-to-end du parcours prière.
- Observabilité : logs structurés sans contenu privé, métriques techniques, tracing avec attributs non sensibles et alertes d'erreur.
- Environnements distincts local / staging / production, secrets via gestionnaire sécurisé ; sauvegardes et exercices de restauration.
- CI : format/lint, tests, contrôle dépendances, secret scanning et revue humaine avant déploiement.
- Une vulnérabilité critique, l'exposition de données sensibles ou l'échec d'un contrôle d'accès bloque la livraison.

## 8. Décision d'architecture
**Pas de microservices au MVP.** Extraire éventuellement des services plus tard, avec preuves de besoin et ADR. Voir [ENGINEERING.md](ENGINEERING.md) et [API-CONTRACTS.md](API-CONTRACTS.md).
