<div align="center">

# 🙏 MonEglise.

### Vous rapprocher de l’Église et de Dieu.

**PRAYER FIRST · FAITH & COMMUNITY · BUILT IN AFRICA**

🇨🇮 **Né en Côte d’Ivoire** &nbsp; | &nbsp; 🌍 **Conçu pour l'Afrique francophone et les communautés chrétiennes partout dans le monde**

[![Website](https://img.shields.io/badge/Website-moneglise.ci-176B47?style=for-the-badge)](https://moneglise.ci)
![Platform](https://img.shields.io/badge/Platform-Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![API](https://img.shields.io/badge/Backend-Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Stage](https://img.shields.io/badge/Stage-MVP%20in%20development-E8A33D?style=for-the-badge)

**Confiez votre intention. Prions ensemble. Grandissons en communauté.**

Une expérience chrétienne de prière participative où chacun peut être écouté, accompagné et soutenu — **sans obligation d’appartenir à une Église**.

[Notre vision](#-notre-vision) · [Expérience](#-les-trois-piliers) · [Technologie](#-notre-architecture) · [Roadmap](#-feuille-de-route) · [Principes](#-nos-engagements)

</div>

---

## 🌱 Notre vision

Nous croyons que le numérique peut rapprocher les personnes autour d’un geste universel : **prier les uns pour les autres**.

MonEglise ne veut pas devenir un énième logiciel de gestion paroissiale ou un réseau social généraliste. Notre ambition est de faire de **la prière le produit principal**, puis d'offrir progressivement aux fidèles et aux Églises des outils utiles pour vivre la fraternité au quotidien.

> **Une intention partagée peut devenir une multitude de prières reçues.**

MonEglise s’adresse aux communautés **catholiques, protestantes et évangéliques**, dans le respect de leurs traditions, ainsi qu’aux personnes non affiliées à une institution religieuse.

### 🌍 Nos racines et notre ambition

- 🇨🇮 **Côte d’Ivoire — origine du projet** : conception et premiers travaux de développement.
- 🌍 **Afrique francophone — ambition d’expansion** : interface et expérience adaptées aux usages mobiles et aux réalités locales.
- 🌐 **Ouverture internationale — vision** : accueillir progressivement toute personne souhaitant prier ou demander une prière.

**Ces zones d’ambition ne constituent pas une annonce de déploiement commercial ou de disponibilité officielle dans les pays concernés.**

---

## ✨ Les trois piliers

<table>
<tr>
<td width="33%" valign="top">

### 🙏 Prière

**Je confie mon intention et j'écoute les prières reçues.**

- Publier une intention de prière.
- Découvrir les intentions de la communauté.
- Prier pour une personne, gratuitement.
- Recevoir des prières écrites et vocales.
- Écouter et conserver ses réponses autorisées.

</td>
<td width="33%" valign="top">

### 🤝 Fraternité

**Je prie pour quelqu'un et lui transmets des Amens.**

- Faire savoir « Je prie pour toi ».
- Offrir sa présence et une prière personnelle.
- Envoyer des Amens en signe de soutien.
- Favoriser la réciprocité et l'entraide.
- Ne jamais conditionner la prière à un paiement.

</td>
<td width="34%" valign="top">

### ⛪ Communauté

**Je soutiens mon Église et ses projets grâce aux Amens.**

- Rejoindre librement une ou plusieurs Églises.
- Suivre leurs intentions communautaires.
- Recevoir, à terme, annonces et prières audio.
- Participer volontairement à des projets.
- Contribuer via un dispositif financier conforme.

</td>
</tr>
</table>

## 💬 Une expérience simple, profondément humaine

```text
UNE INTENTION                UNE COMMUNAUTÉ                  UN SOUTIEN
      🙏                            🎙️                            ❤️
Je partage ce             Des personnes prient         J'écoute leurs prières,
que je traverse           pour moi, par texte         puis je prie à mon tour
                          ou message vocal            pour quelqu'un d'autre
```

**Notre principe :** ouvrir MonEglise ne doit pas ressembler à remplir un formulaire administratif. L'utilisateur doit pouvoir découvrir une intention et prier en quelques gestes.

Le produit est **ouvert sans rattachement obligatoire à une Église**. Les communautés peuvent disposer d'espaces dédiés, et les personnes conservent le choix de leur niveau de visibilité.

---

## 🪙 Amen — une unité de générosité à concevoir avec responsabilité

Dans le modèle produit envisagé :

| Interaction | Expérience prévue |
|:--|:--|
| **Achat** | Référence proposée : **1 Amen = 10 XOF**, paiement via un prestataire intégré par GeniusPay. |
| **Entre fidèles** | Un Amen transmis représente un **soutien symbolique** ; aucun retrait en FCFA par le destinataire individuel. |
| **Vers une Église** | Les Amens donnés à une Église vérifiée pourraient donner lieu à une **contrepartie financière**. |
| **Prière** | Les intentions, les prières et la solidarité spirituelle restent **gratuites**. |

> ⚠️ **Fonctionnalité en conception, non annoncée comme opérationnelle.** Des Amens achetés contre des fonds, transférables entre personnes et donnant lieu à un règlement financier pour des Églises peuvent relever de la réglementation des paiements ou de la monnaie électronique. Leur activation réelle dépend d'une validation juridique, de contrats avec les partenaires habilités, des exigences de conformité et des règles des plateformes mobiles. Une absence de retrait en FCFA pour les particuliers ne suffit pas à supprimer ces obligations.

**Nous ne vendons pas la prière.** Aucun montant ne donne droit à une bénédiction, une intervention spirituelle prioritaire ou un résultat garanti.

---

## 🛠️ Notre architecture

Nous développons un **MVP mobile-first**, en privilégiant la fiabilité, la sécurité et la simplicité.

| Domaine | Choix technique |
|:--|:--|
| **Application mobile** | Flutter / Dart — Android & iOS |
| **Backend** | Go — monolithe modulaire et workers |
| **API** | REST / JSON — contrat OpenAPI |
| **Données** | PostgreSQL |
| **Cache & limites** | Redis selon les besoins |
| **Prières vocales** | Stockage objet compatible S3, privé et sécurisé |
| **Notifications** | Push et notifications consenties |
| **Paiements à l'étude** | GeniusPay et partenaires financiers autorisés |
| **Livraison** | CI/CD, environnements isolés, tests et observabilité |

### 🔐 Confiance avant tout

Les intentions peuvent contenir des informations très personnelles. Notre conception exige :

- La confidentialité des intentions et des enregistrements vocaux, selon la visibilité choisie.
- Un contrôle des accès côté serveur, y compris pour chaque média audio.
- Des systèmes de signalement, modération, blocage et prévention des abus.
- La séparation des espaces communautaires et la protection des données sensibles.
- Une authentification sécurisée, des journaux d'audit et une gestion stricte des secrets.
- Une conformité évaluée avant tout lancement de transactions financières réelles.

La sécurité et le respect des personnes font partie des exigences du produit, et non d'une fonctionnalité optionnelle.

---

## 🚀 Feuille de route

| Étape | Objectif | État |
|:--|:--|:--|
| **01 — Foundations** | Base Flutter + Go, identité, environnement, back-office de modération | 🧭 Planifié |
| **02 — Prayer MVP** | Intentions, réponses écrites et vocales, écoute sécurisée | 🧭 Planifié |
| **03 — Communities** | Églises vérifiées, suivi facultatif et intentions communautaires | 🧭 Planifié |
| **04 — Amens** | Registre, achats et dons, sous réserve d'approbation réglementaire | 🔒 Conditionnel |
| **05 — Church Life** | Annonces audio, SMS et campagnes de projets | 💡 Envisagé |

**Premier jalon produit :** une personne publie une intention, une autre lui adresse une prière vocale, et la première peut l'écouter de manière privée et sécurisée.

*Cette roadmap indique des intentions de développement et ne garantit aucune date de sortie.*

---

## 🧭 Nos engagements

**1. La prière d’abord.** Chaque décision doit améliorer l’acte de prier pour une personne ou de recevoir une prière.

**2. Accessibilité.** Smartphones Android et iOS, connexions limitées, parcours simples et coûts techniques maîtrisés.

**3. Respect des confessions.** MonEglise est une infrastructure numérique, pas une autorité religieuse ni une doctrine nouvelle.

**4. Respect des personnes.** Pas de manipulation émotionnelle, de vente de bénédictions ou de promesses de guérison.

**5. Transparence financière.** La valeur des Amens, les frais, les bénéficiaires et les règlements doivent être explicites et conformes.

**6. Ingénierie responsable.** Documentation, revues de code, confidentialité, sécurité et traçabilité dès le MVP.

---

## 👩🏽‍💻 Collaboration & engineering

Notre organisation GitHub accueille les travaux techniques du produit. Les développements applicatifs et les configurations sensibles sont hébergés dans des dépôts dédiés, avec les autorisations adaptées.

- **Mobile engineering** — Flutter, expérience et accessibilité.
- **Backend engineering** — Go, API, persistance et sécurité.
- **Trust & Safety** — Modération, vie privée et intégrité des interactions.
- **Payment engineering** — Conception des Amens et intégrations réglementées.
- **Product & Design** — Recherche utilisateurs, qualité des parcours, pilotes.

📚 Les contributeurs autorisés peuvent consulter la documentation du dépôt [`.github`](https://github.com/MonEglise/.github) et ses règles de contribution.

---

<div align="center">

### « La prière nous rapproche. La fraternité nous unit. »

**MonEglise. — Vous rapprocher de l’Église et de Dieu.**

🇨🇮 Made with purpose in Côte d’Ivoire · 🌍 Designed with Africa in mind

[🌐 Découvrir MonEglise](https://moneglise.ci)

<sub>MonEglise est développé dans l'écosystème technologique GENIUS GROUPS. Le nom d'une organisation GitHub ne vaut pas immatriculation d'une entité juridique.</sub>

</div>
