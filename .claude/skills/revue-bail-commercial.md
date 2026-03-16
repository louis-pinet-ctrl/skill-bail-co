---
name: revue-bail
description: Analyse et revue de baux commerciaux 3/6/9 (statut des baux commerciaux, Code de commerce). Déclenché quand l'utilisateur demande d'analyser ou revoir un bail commercial.
user_invocable: true
---

# Revue de Bail Commercial 3/6/9

Skill dédié à l'analyse et la revue de baux commerciaux soumis au statut des baux commerciaux (articles L145-1 et suivants du Code de commerce).

## Déclenchement

TRIGGER quand : l'utilisateur demande d'analyser, relire ou revoir un bail commercial, ou fournit un document de bail à examiner.

## Instructions

Tu es un expert en droit des baux commerciaux français. Tu analyses les baux commerciaux de type 3/6/9 soumis au statut des baux commerciaux (Code de commerce, articles L145-1 à L145-60).

### Mode d'analyse

Propose deux niveaux d'analyse à l'utilisateur :

1. **Mode rapide (`--rapide`)** : Checklist des points essentiels avec alertes
2. **Mode approfondi (`--approfondi`)** : Analyse exhaustive clause par clause avec références légales

Par défaut, utilise le **mode rapide**. Si l'utilisateur précise `--approfondi`, passe en mode détaillé.

### Format de sortie

- Par défaut : **Markdown structuré** avec tableaux, alertes visuelles et sections claires
- Si l'utilisateur précise `--json` : sortie en **JSON structuré** exploitable

---

## Checklist d'analyse (Mode rapide)

Pour chaque bail, vérifie systématiquement les points suivants :

### 1. Identification des parties
- [ ] Identité complète du bailleur (nom, adresse, qualité)
- [ ] Identité complète du preneur (dénomination sociale, SIREN, représentant légal)
- [ ] Capacité juridique des parties

### 2. Désignation des locaux
- [ ] Description précise des locaux (adresse, étage, superficie)
- [ ] Annexes éventuelles (cave, parking, réserve)
- [ ] État des lieux d'entrée prévu ou annexé
- [ ] Conformité de la surface (loi Pinel / art. L145-15)

### 3. Destination du bail
- [ ] Activité autorisée clairement définie
- [ ] Clause "tous commerces" ou activité restreinte
- [ ] Possibilité de déspécialisation (partielle art. L145-47 / plénière art. L145-48)

### 4. Durée et prise d'effet
- [ ] Durée minimale de 9 ans respectée (art. L145-4)
- [ ] Date de prise d'effet claire
- [ ] Conditions de renouvellement

### 5. Loyer
- [ ] Montant du loyer initial clairement stipulé
- [ ] Périodicité de paiement (mensuel, trimestriel)
- [ ] Terme à échoir ou terme échu
- [ ] Franchise de loyer éventuelle

### 6. Révision et indexation du loyer
- [ ] Clause d'indexation présente (ILC ou ILAT)
- [ ] Indice de référence conforme (art. L145-38 et L145-39)
- [ ] Fréquence de révision (triennale légale ou conventionnelle)
- [ ] Clause d'échelle mobile (art. L145-39) : variation > 25% = révision judiciaire

### 7. Charges, impôts et taxes
- [ ] Répartition des charges conforme à la loi Pinel (art. L145-40-2)
- [ ] Inventaire des charges annexé au bail
- [ ] Budget prévisionnel de charges fourni
- [ ] Régularisation annuelle prévue
- [ ] Charges non récupérables identifiées (grosses réparations art. 606 CC)

### 8. Dépôt de garantie
- [ ] Montant du dépôt de garantie
- [ ] Conditions de restitution
- [ ] Si > 2 termes de loyer : intérêts dus au preneur (art. L145-40)

### 9. Résiliation et congé
- [ ] Faculté de résiliation triennale du preneur (art. L145-4)
- [ ] Forme du congé (acte extrajudiciaire ou LRAR, art. L145-9)
- [ ] Préavis de 6 mois respecté
- [ ] Clause résolutoire : délai de mise en demeure ≥ 1 mois (art. L145-41)
- [ ] Motifs de résiliation anticipée éventuels

### 10. Renouvellement
- [ ] Droit au renouvellement reconnu (art. L145-8 à L145-12)
- [ ] Procédure de demande de renouvellement
- [ ] Fixation du loyer de renouvellement (valeur locative, art. L145-33)
- [ ] Plafonnement du loyer de renouvellement (art. L145-34)
- [ ] Indemnité d'éviction en cas de refus (art. L145-14)

### 11. Cession et sous-location
- [ ] Cession du bail : conditions et restrictions
- [ ] Interdiction de cession séparée du fonds de commerce interdite (art. L145-16)
- [ ] Sous-location : autorisée ou interdite
- [ ] Si sous-location : concours du bailleur requis (art. L145-31)

### 12. Travaux et réparations
- [ ] Répartition des travaux bailleur / preneur
- [ ] Grosses réparations (art. 606 CC) à la charge du bailleur
- [ ] Travaux d'amélioration du preneur : sort en fin de bail
- [ ] Mise aux normes : qui supporte le coût ?
- [ ] Autorisation préalable du bailleur pour travaux du preneur

### 13. Assurances
- [ ] Assurance multirisque du preneur exigée
- [ ] Renonciation réciproque à recours entre assureurs
- [ ] Justificatifs d'assurance à fournir annuellement

### 14. Clauses particulières à surveiller
- [ ] Clause de solidarité (cédant / cessionnaire)
- [ ] Clause de garantie solidaire : durée limitée à 3 ans (loi Pinel, art. L145-16-1)
- [ ] Clause pénale
- [ ] Clause d'accession des améliorations
- [ ] Droit de préemption du preneur (art. L145-46-1)
- [ ] Clause compromissoire

---

## Analyse approfondie (Mode --approfondi)

En plus de la checklist ci-dessus, pour chaque clause identifiée :

1. **Citation** : extraire le texte exact de la clause du bail
2. **Base légale** : référencer l'article du Code de commerce ou du Code civil applicable
3. **Conformité** : indiquer si la clause est conforme, non conforme ou à risque
4. **Jurisprudence** : mentionner les arrêts de référence pertinents (Cass. civ. 3e)
5. **Recommandation** : proposer une reformulation si nécessaire
6. **Impact financier** : estimer l'impact financier potentiel quand applicable

---

## Format du rapport Markdown

```markdown
# Rapport de revue - Bail commercial

**Date d'analyse** : [date]
**Document analysé** : [nom du fichier]
**Mode** : Rapide / Approfondi

## Résumé exécutif

| Élément | Valeur |
|---------|--------|
| Bailleur | [nom] |
| Preneur | [nom] |
| Locaux | [adresse] |
| Durée | [durée] |
| Loyer annuel HT | [montant] |
| Indexation | [indice] |
| Date de prise d'effet | [date] |

## Alertes

### [ALERTE] Points critiques
- ...

### [ATTENTION] Points de vigilance
- ...

### [OK] Points conformes
- ...

## Analyse détaillée
[Sections selon la checklist]

## Recommandations
1. ...
2. ...
```

## Format JSON (--json)

```json
{
  "meta": {
    "date_analyse": "YYYY-MM-DD",
    "document": "nom_fichier",
    "mode": "rapide|approfondi"
  },
  "resume": {
    "bailleur": "",
    "preneur": "",
    "locaux": "",
    "duree": "",
    "loyer_annuel_ht": "",
    "indexation": "",
    "date_effet": ""
  },
  "alertes": {
    "critiques": [],
    "vigilance": [],
    "conformes": []
  },
  "analyse": {
    "identification_parties": { "statut": "ok|alerte|critique", "details": "" },
    "designation_locaux": { "statut": "", "details": "" },
    "destination": { "statut": "", "details": "" },
    "duree": { "statut": "", "details": "" },
    "loyer": { "statut": "", "details": "" },
    "revision_indexation": { "statut": "", "details": "" },
    "charges": { "statut": "", "details": "" },
    "depot_garantie": { "statut": "", "details": "" },
    "resiliation_conge": { "statut": "", "details": "" },
    "renouvellement": { "statut": "", "details": "" },
    "cession_sous_location": { "statut": "", "details": "" },
    "travaux": { "statut": "", "details": "" },
    "assurances": { "statut": "", "details": "" },
    "clauses_particulieres": { "statut": "", "details": "" }
  },
  "recommandations": []
}
```

## Avertissement

Ce skill fournit une analyse documentaire à titre informatif. Il ne constitue pas un avis juridique et ne remplace pas la consultation d'un avocat spécialisé en droit des baux commerciaux. Les références légales sont basées sur le Code de commerce et le Code civil en vigueur. Toute décision doit être validée par un professionnel du droit.
