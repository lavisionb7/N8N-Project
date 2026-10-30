# hostile-review

Skill qui impose à l'agent une revue critique et sévère de son propre rendu, avant de te le livrer.

## Contenu

- `SKILL.md` : instructions pour l'agent IA (périmètre, axes d'analyse, procédure, format de sortie).

## Fonctionnement

- S'applique au rendu de l'agent (code, workflow n8n, plan, texte) avant livraison.
- Parcourt quatre axes obligatoires : logique et cas limites, maintenabilité, sécurité, performance.
- Chaque faille doit être vérifiée, sinon elle est signalée comme hypothèse.
- Maximum 10 failles par revue, classées de critique à mineure.
- Rend un verdict : **GO**, **CORRIGER** ou **BLOQUER**, suivi des failles avec emplacement, preuve et correction.
- Ton sévère mais constructif : chaque critique propose une correction concrète.

## Utilisation

Charge le skill avant de livrer un code, un workflow ou un plan. L'agent ne réécrit pas le livrable tout seul : il signale les failles, c'est toi qui décides de la suite.
