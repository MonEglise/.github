# MonEglise — Engineering handbook

**Portée :** standards de développement publics et génériques. Les détails internes de production restent dans un dépôt privé.

## 1. Principes
- **Prayer-first**, sécurité et confidentialité par défaut, petites livraisons vérifiables.
- Ne pas transformer le MVP en ERP d'Église ni en outil de monétisation de la prière.
- Préférer **monolithe Go modulaire** et application Flutter feature-first à la fragmentation en microservices.
- Respecter les exigences du [brief produit](PRODUCT.md) et de la [référence d'architecture](ARCHITECTURE.md).
- En cas d'ambiguïté, **documenter l'hypothèse et demander revue** ; ne pas inventer des droits, des politiques financières ou des endpoints.

## 2. Flutter / Dart
- Structure recommandée : `lib/features/<feature>/{presentation,domain,data}/`, `lib/core/`; utiliser des dépendances explicites.
- Séparer UI, états et accès réseau ; widgets aussi petits et testables que possible ; internationalisation dès le début.
- Écrans prioritaires : onboarding, fil, détail intention, création d'intention, réponse audio, notifications, profil.
- Prévoir accessibilité (labels, taille de texte), états hors-ligne, redémarrage réseau, refus microphone et permissions système.
- Jamais de token privilégié dans le binaire ni de contrôle des permissions reposant exclusivement sur le mobile.
- Lancer `dart format`, analyse statique, tests unitaires/widget et tests de parcours critiques.

## 3. Go
- Structure recommandée : `cmd/api`, `cmd/worker`, `internal/{identity,prayers,communities,media,moderation,notifications,ledger}`.
- Séparer domaine, transport HTTP, persistence et intégrations externes ; injections de dépendances explicites.
- `context.Context` et deadlines sur entrées/sorties, fermeture correcte des ressources, requêtes paramétrées, migrations revues.
- Tests `go test ./...`, `go vet ./...`, formatage `gofmt`, outils d'analyse convenus par l'équipe.
- Autorisation par ressource + community scope **côté backend** pour chaque action et média.
- Erreurs structurées sans divulguer secrets, informations personnelles ou détails d'infrastructure.

## 4. PostgreSQL, Redis et media
- PostgreSQL est la **source de vérité**, Redis n'est pas le registre de solde ni le garant unique des quotas financiers.
- Contraintes SQL et transactions atomiques pour quotas, limites et opérations financières simulées.
- Migrations immuables après déploiement ; tests sur bases éphémères, index justifiés, politiques de rétention.
- Audio privé, métadonnées minimales et accès éphémère autorisé. Pas de buckets publics.

## 5. Git et revue
- Branches courtes : `feat/<scope>`, `fix/<scope>`, `docs/<scope>`, `chore/<scope>`.
- Conventional Commits : `feat:`, `fix:`, `docs:`, `test:`, `security:`.
- Toute PR doit présenter : pourquoi, impact utilisateur, risques confidentialité/sécurité, tests, migrations, stratégie de rollback.
- Deux yeux humains minimum sur les parcours sensibles : identité, modération, audio privé, fonds/Amens.
- Tests et contrôles CI obligatoires ; aucun déploiement production décidé par un agent seul.

## 6. Définition de terminé (DoD)
- [ ] Alignement avec le pilier Prière/Fraternité/Communauté.
- [ ] Critères d'acceptation écrits, tests positifs/négatifs, erreurs et cas mobile hors-ligne.
- [ ] Permissions, confidentialité et logs revus ; aucune donnée personnelle de test dans le repo.
- [ ] Documentation/API et migration mises à jour si nécessaires.
- [ ] CI verte, revue humaine, plan de rollback si comportement sensible.
- [ ] Feature flag fermé par défaut si fonctionnalité financière ou non approuvée.

## 7. Décisions structurantes
Tracer les choix non triviaux en ADR : contexte, options, décision, conséquences, propriétaire et date. Voir [DECISIONS.md](DECISIONS.md).
