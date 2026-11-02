# MonEglise — GitHub Organization

> **MonEglise.** Vous rapprocher de l’Église et de Dieu.

Bienvenue dans le dépôt communautaire et documentaire de l'organisation GitHub **MonEglise**.

Ce dépôt définit la vision produit, les standards techniques et les règles de contribution. Il **ne contient pas** le code source de l'application.

## La vision

**MonEglise est une application centrée sur la prière**, ouverte aux catholiques, protestants, évangéliques et aux personnes qui ne sont rattachées à aucune Église.

- **Prière** — Confier une intention, prier pour autrui, recevoir et écouter des prières textuelles ou vocales.
- **Fraternité** — Soutenir une autre personne en priant pour elle et en lui transmettant des Amens.
- **Communauté** — Rejoindre librement une ou plusieurs Églises et soutenir leurs projets.

La prière est toujours gratuite. Personne ne doit payer pour recevoir une prière, une attention spirituelle ou une promesse de bénédiction.

## MVP et technologie

- **Mobile :** Flutter / Dart — Android et iOS.
- **Backend :** Go, monolithe modulaire et workers.
- **Données :** PostgreSQL, Redis si nécessaire.
- **Audio :** stockage privé compatible S3, accès temporaire et autorisé.
- **API :** REST / OpenAPI, version `/v1`.
- **Paiements envisagés :** GeniusPay et un partenaire financier habilité.

## Documentation

- [Vision et MVP](docs/PRODUCT.md)
- [Architecture Flutter + Go](docs/ARCHITECTURE.md)
- [Système Amen et conditions de conformité](docs/AMENS.md)
- [Roadmap](docs/ROADMAP.md)
- [Contribuer](CONTRIBUTING.md)
- [Politique de sécurité](SECURITY.md)
- [Code de conduite](CODE_OF_CONDUCT.md)

## Réglementation des Amens

Le concept prévoit **1 Amen = 10 XOF à l'achat**. Les transferts entre personnes sont conçus comme des marques symboliques de soutien, sans retrait individuel en FCFA. Une Église vérifiée pourrait recevoir des Amens donnant lieu à un règlement financier.

Cette présentation **n'exclut pas** la qualification de valeur monétaire réglementée. Aucun paiement réel, transfert monétisable ou reversement ne doit être activé sans validation juridique et accords avec les prestataires habilités.

## Profil d'organisation

Le fichier [`profile/README.md`](profile/README.md) décrit le produit sur la page de l'organisation GitHub lorsque ce dépôt `.github` est **public**. La mise en public doit être effectuée après validation que tous les contenus publiés sont destinés à la diffusion.

🌐 https://moneglise.ci

*Projet développé dans l'écosystème technologique de GENIUS GROUPS. La création de l'organisation GitHub ne préjuge pas de la constitution juridique d'une entité « MonEglise, Inc. ».*
