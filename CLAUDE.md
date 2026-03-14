# CLAUDE.md

## Skills disponibles

### Revue de bail commercial CHR — Restauration
- **Fichier** : `.claude/skills/revue-bail-commercial.md`
- **Déclenchement** : Quand l'utilisateur demande d'analyser ou revoir un bail commercial, en particulier dans le secteur CHR
- **Modes** : `--rapide` (défaut) | `--approfondi`
- **Formats** : Markdown (défaut) | `--json`
- **Périmètre** : Bail commercial 3/6/9, spécialisé CHR (Cafés, Hôtels, Restaurants)
- **Spécialisation** : Destination restauration, extraction, distinction restauration traditionnelle / rapide / petite restauration

## MCP Servers requis

Ce skill utilise deux MCP servers pour vérifier systématiquement les références légales :

1. **OpenLegi** — Vérification des textes via l'API Légifrance (articles de codes, décrets, jurisprudence)
2. **GoodLegal** — Analyse juridique complémentaire et conformité des clauses

## Utilisation

Pour analyser un bail, fournir le document (PDF, texte, ou copier-coller) et demander une revue :
- Revue rapide : "Analyse ce bail commercial"
- Revue approfondie : "Analyse ce bail commercial --approfondi"
- Sortie JSON : "Analyse ce bail commercial --json"
