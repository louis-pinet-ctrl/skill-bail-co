# skill-bail-co

Skill Claude Code pour la revue de baux commerciaux 3/6/9, spécialisé **CHR (Cafés, Hôtels, Restaurants)** et activités de **restauration**.

## Fonctionnalités

- Analyse automatisée des baux commerciaux soumis au statut des baux commerciaux
- **Spécialisation CHR** : attention particulière à la destination, l'extraction, les licences et normes restauration
- Distinction fine entre restauration traditionnelle, rapide, petite restauration, snack, bar-restaurant
- Vérification systématique des textes juridiques via **OpenLegi** et **GoodLegal** (MCP servers)
- Deux modes d'analyse : rapide (checklist) et approfondi (clause par clause avec références légales vérifiées)
- Sortie en Markdown structuré ou JSON
- Alertes visuelles : points critiques, points de vigilance, points conformes

## Points de contrôle (16 sections)

1. Identification des parties
2. Désignation des locaux
3. **Destination du bail (section critique CHR)** — restauration vs restauration rapide vs petite restauration
4. **Extraction et ventilation (section critique CHR)** — compatibilité avec l'activité
5. Durée et prise d'effet
6. Loyer
7. Révision et indexation
8. Charges, impôts et taxes (conformité loi Pinel)
9. Dépôt de garantie
10. Résiliation et congé
11. Renouvellement
12. Cession et sous-location
13. Travaux et réparations
14. Assurances
15. **Normes et réglementation CHR** — ERP, accessibilité, hygiène, licences
16. Clauses particulières

## MCP Servers requis

| Serveur | Rôle | URL |
|---------|------|-----|
| **OpenLegi** | Vérification des textes légaux via Légifrance | [openlegi.fr](https://www.openlegi.fr) |
| **GoodLegal** | Analyse juridique complémentaire | [goodlegal.fr](https://www.goodlegal.fr) |

## Utilisation

```
# Analyse rapide (défaut)
Analyse ce bail commercial

# Analyse approfondie
Analyse ce bail commercial --approfondi

# Sortie JSON
Analyse ce bail commercial --json
```

## Références légales

- Code de commerce : articles L145-1 à L145-60
- Code civil : articles 606, 1719, 1720
- Loi Pinel (2014) : encadrement des charges et de la garantie solidaire
- Réglementation ERP type N (restauration)
- Règlement CE 852/2004 (hygiène alimentaire)

## Avertissement

Ce skill fournit une analyse documentaire à titre informatif. Il ne constitue pas un avis juridique et ne remplace pas la consultation d'un avocat spécialisé.
