# CLAUDE.md

## Skills disponibles

### Revue de bail commercial
- **Fichier** : `.claude/skills/revue-bail-commercial.md`
- **Déclenchement** : Quand l'utilisateur demande d'analyser ou revoir un bail commercial
- **Modes** : `--rapide` (défaut) | `--approfondi`
- **Formats** : Markdown (défaut) | `--json`
- **Périmètre** : Bail commercial 3/6/9 (statut des baux commerciaux, Code de commerce)

## Utilisation

Pour analyser un bail, fournir le document (PDF, texte, ou copier-coller) et demander une revue :
- Revue rapide : "Analyse ce bail commercial"
- Revue approfondie : "Analyse ce bail commercial --approfondi"
- Sortie JSON : "Analyse ce bail commercial --json"
