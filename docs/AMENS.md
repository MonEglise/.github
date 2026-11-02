# Amens — Concept produit, ledger et conditions d'activation

**Statut : PROPOSÉ / NON AUTORISÉ POUR PRODUCTION FINANCIÈRE.**
Ce document n'est ni une qualification juridique ni une autorisation d'émettre de la monnaie électronique.

## 1. Concept validé pour l'étude
- Parité proposée à l'achat : **1 Amen = 10 XOF**.
- Un fidèle peut acheter des Amens via des moyens de paiement orchestrés par GeniusPay, **si** les accords et autorisations sont obtenus.
- Entre particuliers, offrir des Amens est une expérience **symbolique** ; le particulier ne peut pas retirer les Amens en FCFA.
- Un fidèle peut offrir des Amens à une Église vérifiée ; MonEglise envisage une **contrepartie financière** réglée à celle-ci.
- Les prières, l'enregistrement vocal, l'accès aux intentions et la participation spirituelle ne sont **jamais conditionnés** au montant détenu ou donné.

## 2. Attention : conséquences de la circulation de valeur
Un Amen payé en FCFA, transférable et admis à créer un droit à paiement d'une Église peut être considéré comme une **valeur monétaire stockée et acceptée par des tiers**. Sa présentation « symbolique » entre particuliers et l'absence de retrait individuel **ne neutralisent pas** ce risque.

La BCEAO, un conseil spécialisé et les partenaires financiers doivent déterminer les exigences applicables avant toute collecte et toute mise en circulation réelle. Vérifier également les règles de facturation/dons et les modalités d'achat d'unités dans les stores iOS/Android.

## 3. Circuit conceptuel, sous réserve de validation
```text
1. Achat de 100 Amens pour 1 000 XOF
     -> paiement confirmé par partenaire habilité
2. Crédit de 100 Amens (registre sécurisé)
3. Transfert de 100 Amens à un autre fidèle
     -> aucun cash-out individuel
4. Don de 100 Amens à une Église vérifiée
5. Versement financier vers l'Église selon le dispositif autorisé
```

**Règle d'unicité :** un achat de 1 000 XOF ne peut créer qu'une seule contrepartie financière de 1 000 XOF **brute**. Les transferts n'émettent pas de nouvelles unités ni de nouveaux fonds. Le traitement des frais, retenues, chargebacks et remboursements doit être contractuellement défini.

## 4. Invariants techniques
- Registre **à double entrée**, atomique, immutable en pratique et vérifiable par rapprochement ; montants entiers, aucun flottant pour les Amens ou les XOF.
- Un compte ne peut transférer plus que son solde disponible ; verrouiller ou sérialiser les débits concurrents.
- Références uniques et **idempotency keys** sur achat, transfert, don et règlement.
- Journal d'événements de paiement signé/vérifié, déduplication des webhooks, états `pending/confirmed/failed/reversed` et prise en charge des remboursements.
- Séparer registres d'unités Amen et **comptabilité monétaire** en XOF ; traiter les commissions distinctement.
- Requêtes interdites entre particuliers vers un compte bancaire ou mobile money ; seuls les parcours approuvés sont exposés.
- Comptes Églises vérifiés et bénéficiaires autorisés ; exigences KYC/KYB et antifraude définies avec les partenaires.
- Aucun crédit gratuit de « monnaie » convertible sans sponsor de financement explicite et ledger équilibré.

## 5. Garde-fous UI/UX
- Séparer l'action gratuite « Je prie » de « Offrir des Amens ».
- Ne jamais classer les intentions selon le montant donné.
- Pas de promesse de guérison, d'intercession prioritaire, d'indulgence ou de résultat spirituel en échange d'Amens.
- Afficher la valeur, les frais applicables, les bénéficiaires et les limites avant confirmation.

## 6. Gate de mise en production — tous obligatoires
- [ ] Analyse juridique écrite (monnaie électronique, services de paiement, dons, données personnelles).
- [ ] Accord formel avec le/les établissements financiers habilités et rôles contractuels validés.
- [ ] Vérification des politiques Apple App Store et Google Play concernant unités, dons et moyens de paiement.
- [ ] Schémas de flux de fonds, des responsabilités et de gestion des remboursements approuvés.
- [ ] Audit sécurité du ledger et du webhook, tests de concurrence, double dépense, fraude et réconciliation.
- [ ] Vérification des Églises bénéficiaires, gestion des litiges et information utilisateur.
- [ ] Validation explicite par les responsables Produit, Finances, Sécurité et Juridique.

**Avant ce gate :** mock wallet, unités **fictives et explicitement marquées TEST**, sandbox uniquement ; aucun vrai FCFA et aucun token réutilisable contre une valeur financière réelle.
