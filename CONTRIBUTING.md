# Contribuer à MonEglise

Merci de contribuer à MonEglise. Ce document s'applique à tous les dépôts de
l'organisation, sauf si un dépôt définit des règles plus strictes (`AGENTS.md`).

## Avant de commencer

1. Lire [PRODUCT.md](docs/PRODUCT.md), [ENGINEERING.md](docs/ENGINEERING.md)
   et [SECURITY-PRIVACY.md](docs/SECURITY-PRIVACY.md).
2. Consulter les instructions spécifiques du dépôt (`AGENTS.md`,
   `README.md`).

## Règles de base

- Branches courtes : `feat/<scope>`, `fix/<scope>`, `docs/<scope>`, `chore/<scope>`.
- Conventional Commits : `feat:`, `fix:`, `docs:`, `test:`, `security:`, `chore:`.
- Petites Pull Requests, CI verte obligatoire, revue humaine requise.
- Une PR décrit : le besoin, les fichiers modifiés, les tests exécutés et leurs
  résultats, les risques (confidentialité, sécurité, finance), les migrations,
  ce qui reste incomplet et la stratégie de rollback.
- Deux revues humaines minimum sur : identité, modération, audio privé,
  autorisations, tout code lié aux Amens ou aux paiements.

## Jamais dans les dépôts

- Secrets, clés, tokens, identifiants, données personnelles réelles, logs ou
  journaux d'incidents.
- Détails d'infrastructure de production (IPs, topologie, chemins internes).
- Fixtures contenant des données de vrais utilisateurs.

## Principes produit non négociables

- La prière est gratuite : aucun paiement ne conditionne une intention ou une
  prière.
- L'appartenance à une Église est facultative.
- Aucune fonctionnalité financière (Amens, achats, transferts, règlements) ne
  peut être activée sans validation juridique, financière et sécurité
  documentée.
- Les permissions sont toujours décidées côté serveur, jamais par le client.
