# skill-bail-co

Skill Claude Code pour la revue de baux commerciaux 3/6/9.

## Fonctionnalités

- Analyse automatisée des baux commerciaux soumis au statut des baux commerciaux
- Checklist de 14 points de contrôle couvrant toutes les clauses essentielles
- Deux modes d'analyse : rapide (checklist) et approfondi (clause par clause avec références légales)
- Sortie en Markdown structuré ou JSON
- Alertes visuelles : points critiques, points de vigilance, points conformes

## Points de contrôle

1. Identification des parties
2. Désignation des locaux
3. Destination du bail
4. Durée et prise d'effet
5. Loyer
6. Révision et indexation
7. Charges, impôts et taxes (conformité loi Pinel)
8. Dépôt de garantie
9. Résiliation et congé
10. Renouvellement
11. Cession et sous-location
12. Travaux et réparations
13. Assurances
14. Clauses particulières

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
- Code civil : article 606 (grosses réparations)
- Loi Pinel (2014) : encadrement des charges et de la garantie solidaire

## Avertissement

Ce skill fournit une analyse documentaire à titre informatif. Il ne constitue pas un avis juridique et ne remplace pas la consultation d'un avocat spécialisé.
