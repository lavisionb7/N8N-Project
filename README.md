# N8N-Project

Projet regroupant un workflow n8n (**GymTrack**, suivi de musculation), des skills pour agents IA et une démo vidéo.

## GymTrack

Application de suivi de musculation construite dans n8n. Elle tient lieu de back-end et sert aussi une interface mobile, générée par le workflow lui-même.

**Ce que fait l'application**

- Programme les séances (5 routines) et ajoute, modifie ou retire des exercices depuis un catalogue Lyfta.
- Enregistre chaque série (poids, reps, notes) dans une table n8n `DB_LOGS`.
- Calcule une **surcharge progressive** pour chaque exercice : fourchette de 6 à 10 reps, +1 kg quand 3×10 sont validés, allègement si une série passe sous 6 reps.
- Donne un **avis de coach** à la demande, généré par Gemini à partir de la séance saisie et de l'historique.
- Envoie un **bilan hebdomadaire** par e-mail : séances, séries, tonnage et paliers atteints.

**Pourquoi ce design**

- Tout est dans un seul workflow, pour garder une logique lisible de bout en bout : saisie, stockage, calcul, affichage.
- Les règles de progression sont du code simple et explicite (`coachFor`), pas une boîte noire : on peut les relire et les ajuster.
- Les secrets (clés Gemini et Lyfta) restent dans les credentials de n8n, jamais dans le code.
- Le versionnement passe par `n8ncli` : le workflow est stocké en TypeScript, ce qui permet de le relire, de le comparer et de le valider avant chaque envoi vers n8n.

**Fichiers**

- `Workflow/GymTrack.workflow.ts` : workflow exporté. Les identifiants sont remplacés par des placeholders (`<CLE_API_GEMINI>`, `<CLE_API_LYFTA>`, `<URL_APP_N8N>`) à renseigner dans n8n avant utilisation.

## Skills pour agents IA

Quatre skills accompagnent le projet. Elles montrent comment encadrer un agent avec des règles précises, plutôt que de lui laisser une réponse libre.

- `Skill/interview/` : simulation d'entretien d'embauche. L'agent joue le recruteur et le coach, donne un feedback après chaque réponse et finit par une grille d'évaluation.
- `Skill/doubt-driven-dev/` : impose un doute méthodique aux réponses non triviales : hypothèses explicites, tentatives de réfutation, revue par un regard neuf.
- `Skill/hostile-review/` : revue critique du code ou d'un plan. *(à compléter)*
- `Skill/N8NCLI/` : pilotage de n8n depuis le terminal avec le CLI `n8ncli` (pull, validate, push, test).

## Structure

- `Workflow/` : workflow GymTrack, en TypeScript (synchronisé avec `n8ncli`).
- `Skill/` : skills pour agents IA.
- `Video/` : vidéo de démonstration du workflow et son transcript. *(à venir)*

## Outils

- [n8n](https://n8n.io) et le CLI [`@workflows-accelerator/n8n-cli`](https://www.npmjs.com/package/@workflows-accelerator/n8n-cli).
