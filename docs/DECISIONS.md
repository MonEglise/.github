# Décisions et hypothèses — MonEglise

Ce registre sépare les **décisions produit**, les **hypothèses à confirmer** et les **options techniques** ; ce n'est pas un procès-verbal officiel du Board.

| ID | Sujet | Statut | Conséquence |
|---|---|---|---|
| PRD-001 | La prière est le produit principal, pas l'administration d'Église | **Orientation retenue** | toute fonctionnalité doit justifier son utilité spirituelle |
| PRD-002 | L'appartenance à une Église reste facultative | **Orientation retenue** | communauté ouverte et espaces institutionnels |
| PRD-003 | Prière toujours gratuite | **Règle produit** | pas de paywall, priorité payante ou promesse spirituelle |
| TECH-001 | Mobile Flutter et API Go | **Choix retenu** | architecture modulaire, contrats REST |
| TECH-002 | PostgreSQL, stockage audio privé, Redis au besoin | **Architecture proposée** | à confirmer avec benchmarks/tests |
| AMEN-001 | Parité souhaitée 1 Amen = 10 XOF | **Modèle proposé** | aucune mise en production sans conformité |
| AMEN-002 | Entre fidèles symbolique sans cash-out, Églises potentiellement payées | **Modèle proposé** | audit juridique sur valeur transférable |
| MVP-001 | 5 intentions mises en avant / jour / communauté | **Hypothèse à tester** | quotas et file d'attente |
| MVP-002 | Premier parcours : publier une intention, recevoir et écouter une prière vocale | **Jalon MVP** | P0 produit |

## Proposition de modèle ADR pour décisions techniques

```markdown
# ADR-XXXX — Titre
- Statut : proposé | accepté | remplacé
- Date :
- Responsables :
- Contexte et problème :
- Options évaluées :
- Décision :
- Conséquences / risques :
- Conditions de réexamen :
```

Toute modification des règles financières, des rôles, des accès, de la confidentialité ou de la gratuité de la prière nécessite validation explicite, et non une décision autonome d'un agent IA.
