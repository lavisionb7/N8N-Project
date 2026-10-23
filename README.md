# N8N-Project

Projet regroupant un workflow n8n, des skills pour agents IA et une démo vidéo.

## Structure

- `Workflow/` : le workflow n8n, en TypeScript (synchronisé avec `n8ncli`).
- `Skill/` : skills pour agents IA
  - `interview/` : simulation d'entretien d'embauche (recruteur / coach, feedback et grille d'évaluation).
  - `doubt-driven-dev/` : doute méthodique et vérifiable sur les réponses non triviales (hypothèses, réfutation, revue).
  - `hostile-review/` : revue critique (à compléter).
  - `N8NCLI/` : pilotage de n8n avec le CLI `n8ncli`.
- `Video/` : vidéo de démonstration du workflow et son transcript.

## Outils

- [n8n](https://n8n.io) et le CLI [`@workflows-accelerator/n8n-cli`](https://www.npmjs.com/package/@workflows-accelerator/n8n-cli).
