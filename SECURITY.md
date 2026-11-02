# Politique de sécurité

## Signaler une vulnérabilité

**Ne pas ouvrir d'issue publique** pour un problème de sécurité ou de
confidentialité. MonEglise traite des contenus particulièrement sensibles
(convictions religieuses, prières vocales, situations personnelles).

Utiliser **GitHub Private Vulnerability Reporting** (onglet *Security* du
dépôt concerné) lorsqu'il est disponible, ou le canal privé d'équipe défini en
interne. Une adresse de contact sécurité publique sera publiée ici avant tout
lancement public.

Inclure : description, impact potentiel, étapes de reproduction avec données
synthétiques uniquement. Ne jamais joindre de données réelles d'utilisateurs,
de secrets ou de journaux non caviardés.

## Périmètre

| Dans le périmètre | Hors périmètre |
| --- | --- |
| API MonEglise et application mobile | Vulnérabilités des fournisseurs sans impact MonEglise |
| Contournements d'autorisation (IDOR/BOLA), accès inter-communautés | Ingénierie sociale des équipes |
| Exposition d'intentions, de prières ou de médias | Attaques nécessitant un accès physique |
| Fuite de secrets ou de données personnelles | Signalements automatisés sans démonstration |

Les dépendances tierces (GeniusPay, fournisseurs SMS/push, services cloud)
sont traitées selon leur propre politique de divulgation.

## Réponse

Accusé de réception sous quelques jours ouvrés ; correctifs prioritaires sur
les vulnérabilités touchant la confidentialité des prières, l'accès aux médias
ou les intégrités financières. Aucune divulgation coordonnée n'est engagée
avant l'existence d'un environnement de production.
