# N8NCLI

Skill pour piloter n8n depuis un terminal avec le CLI `n8ncli` (version 1.2.x).

## Contenu

- `SKILL.md` : instructions pour un agent IA (commandes, workflow-as-code, validation, tests).

## Commandes principales

- `n8ncli pull` : récupère les workflows n8n et les convertit en fichiers TypeScript.
- `n8ncli validate` : valide les fichiers locaux contre les schémas n8n.
- `n8ncli status` / `n8ncli diff` : compare local et distant.
- `n8ncli push [--dry-run] <fichier>` : envoie les modifications vers n8n.
- `n8ncli test` / `n8ncli exec` : teste ou déclenche un workflow.

## Installation

```bash
npm install -g @workflows-accelerator/n8n-cli@latest
```
