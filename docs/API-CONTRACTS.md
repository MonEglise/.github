# MonEglise — Contrats REST v1 (proposition)

**Statut : DRAFT.** Les chemins et schémas sont des propositions à matérialiser dans un OpenAPI versionné dans le futur dépôt backend. Ne pas considérer ce fichier comme une spécification d'API déjà déployée.

## 1. Conventions
- Préfixe `/v1`, JSON UTF-8, timestamps ISO 8601 UTC, identifiants opaques UUID/ULID.
- `Authorization: Bearer <token>` pour les opérations requérant une session ; autorisation effective vérifiée à chaque requête.
- `Idempotency-Key` obligatoire pour les mutations financières et recommandé pour les mutations sensibles réessayables.
- Erreurs structurées : `{ "error": { "code": "STRING", "message": "safe message", "request_id": "..." } }` (pas de données personnelles internes).
- Pagination avec `limit` borné et `cursor` opaque ; pas de fuite d'existence des intentions privées par erreurs différenciées.

## 2. Authentification et compte
| Méthode | Route | But |
|---|---|---|
| POST | `/v1/auth/otp/request` | OTP, limité par utilisateur et IP |
| POST | `/v1/auth/otp/verify` | validation OTP et session (récupération par numéro) |
| POST | `/v1/auth/device` | session liée à l'appareil, compte sans numéro (PRD-004) |
| POST | `/v1/me/phone/verify` | validation facultative du numéro du compte courant |
| GET | `/v1/me` | profil authentifié |
| PATCH | `/v1/me` | données éditables et préférences |
| DELETE | `/v1/me` | demande de suppression et suivi selon rétention légale |

**Attention :** vérifier avant la production les conditions du fournisseur SMS/OTP, la durée des jetons, le rate limiting et les stratégies anti-énumération.

## 3. Intentions et prières
| Méthode | Route | But |
|---|---|---|
| GET | `/v1/intentions` | fil selon droits du demandeur |
| POST | `/v1/intentions` | créer (status pending, pas auto-publication) |
| GET | `/v1/intentions/{id}` | détail autorisé |
| PATCH | `/v1/intentions/{id}` | modifier selon statut et rôle |
| POST | `/v1/intentions/{id}/pray` | enregistrer une participation gratuite |
| POST | `/v1/intentions/{id}/responses` | prière texte ou référence audio autorisée |
| GET | `/v1/intentions/{id}/responses` | réponses filtrées par autorisation |
| POST | `/v1/media/upload-url` | demander upload direct limité d'audio |
| GET | `/v1/media/{id}/playback` | obtenir lecture éphémère après contrôle d'accès |
| POST | `/v1/reports` | signaler contenu/utilisateur |

**Exemple d'intention :**
```json
{
  "text": "Priez pour ma famille.",
  "visibility": "community",
  "community_id": "opaque-community-id"
}
```
Le serveur valide l'appartenance/visibilité et met `status=pending` si la modération est requise.

**Réponse vocale :** l'API prend une référence de média finalisé, jamais une URL arbitraire de fournisseur ni un stockage public.

## 4. Communautés
| Méthode | Route | But |
|---|---|---|
| GET | `/v1/communities` | catalogue des Églises vérifiées |
| POST | `/v1/communities/{id}/join` | rejoindre/suivre selon politique de l'Église |
| DELETE | `/v1/communities/{id}/membership` | quitter selon droits |
| GET | `/v1/communities/{id}/intentions` | intentions visibles de cette communauté |

## 5. Amens — interfaces à garder désactivées
| Méthode | Route | But |
|---|---|---|
| GET | `/v1/amens/balance` | solde autorisé |
| POST | `/v1/amens/purchases` | initier achat sous cadre autorisé |
| POST | `/v1/amens/transfers` | transfert entre personnes |
| POST | `/v1/churches/{id}/donations` | don vers Église vérifiée |

**Ne pas** créer de route opérationnelle de cash-out pour les particuliers. Les webhooks prestataires sont **authentifiés**, strictement séparés de l'API cliente et traités idempotemment.

## 6. Invariants pour tous les endpoints
Contrôle accessibilité + journalisation sans contenu privé, résilience retries, limites taille/durée, validation entrée, politique de consentement, réponse `403/404` n'exposant pas les contenus non autorisés, test de changement de communauté et d'identité.
