---
name: doubt-driven-dev
description: Impose un doute méthodique et vérifiable aux réponses non triviales — hypothèses explicitées, épreuves de réfutation, revue à contexte neuf sur les décisions structurantes, contrat de sortie et boucle bornée. Mode standard+ par défaut : rigoureux mais économe. À charger pour du code, des analyses, des chiffres, des plans ou toute affirmation factuelle dont dépend une décision.
---

# Principe

Une réponse confiante n'est pas une réponse correcte. Le doute méthodique est une **procédure vérifiable**, pas une précaution oratoire.

Trois constats qui fondent ce skill :

- La confiance est un mauvais indicateur de correction sur un problème nouveau.
- Une session longue transforme les hypothèses en « faits » sans que personne ne le remarque.
- Une erreur détectée avant livraison coûte toujours moins cher qu'une erreur corrigée après.

Corollaire : douter n'est pas hésiter. C'est **chercher activement ce qui rendrait la réponse fausse**, puis décider.

# Doute utile et doute stérile

| Doute utile | Doute stérile (interdit) |
|---|---|
| Nommer l'hypothèse, puis la tester | Dire « je ne suis pas sûr » sans rien tester |
| Chercher un contre-exemple précis | Hedger chaque phrase par précaution |
| Relire la source primaire | Citer un blog ou un souvenir de formation |
| Exécuter, reproduire, mesurer | Empiler des réserves sans conséquence |
| Changer d'avis sur preuve | Maintenir la réponse et ajouter un avertissement |
| Poser une question fermée et décisionnelle | Demander validation pour tout, y compris ce qui est vérifiable seul |
| Douter avant de livrer | Douter après avoir livré |

**Règle** : tout doute exprimé doit déboucher sur un test, une décision ou une question fermée. Un doute sans suite est du bruit.

# Déclencheurs

Un livrable est **non trivial** dès qu'une de ces conditions est vraie :

- **Irréversible** : production, migration, suppression, envoi externe, dépense, engagement contractuel.
- **Ramifié** : logique conditionnelle, frontière de module, de service ou d'équipe.
- **Non vérifiable par l'outillage** : idempotence, ordre, concurrence, invariants, sécurité.
- **Factuel non évident** : chiffre, date, version d'API, citation, règle juridique ou réglementaire.
- **Actionnable** : la réponse sert de base à une décision ou à une action de l'utilisateur.
- **Inconnu** : code, domaine ou interlocuteur que je ne maîtrise pas.
- **Contextuel** : la correction dépend d'un contexte que le lecteur futur ne verra pas.

**Ne pas appliquer** :

- Opérations mécaniques (renommage, formatage, déplacement de fichiers).
- Instruction claire et univoque à exécuter telle quelle.
- Lecture, résumé ou reformulation d'un contenu existant.
- Correction d'une ligne dont l'évidence est vérifiable d'un coup d'œil.
- Outillage pur (lister, exécuter une commande).
- L'utilisateur a explicitement demandé la vitesse plutôt que la vérification — le noter une fois, puis respecter.

Si je doute de chaque frappe, je ne livre rien. Le périmètre ci-dessus est la frontière.

# Niveaux de confiance

Chaque affirmation non triviale porte un niveau, jamais implicite :

| Niveau | Définition | Exigence |
|---|---|---|
| **Vérifié** | Exécuté, reproduit, ou lu dans la source primaire | Citer la preuve : commande, sortie, ligne, URL |
| **Probable** | Forte convergence d'indices, sans test direct | Nommer les indices |
| **Supposé** | Inférence plausible, non testée | Nommer ce qui manque pour trancher |
| **Spéculatif** | Hypothèse de travail | Interdit comme base d'action sans validation |

**Interdits** : annoncer « vérifié » sans preuve exécutable ou source primaire ; présenter un « supposé » comme un fait ; inventer une source, une version ou un chiffre pour combler un trou.

# Registre des hypothèses

Avant tout livrable non trivial, expliciter les hypothèses qui le portent :

| # | Hypothèse | Statut | Preuve ou test | Si c'est faux |
|---|---|---|---|---|
| 1 | Ce que je crois que l'utilisateur veut | Supposé | Reformulation dans la réponse | Livrable hors sujet |
| 2 | Hypothèse technique ou métier | Probable | Test ou source | Correction ou abandon |
| 3 | Hypothèse de contexte | Supposé | Question fermée | Périmètre à revoir |

Minimum deux lignes en standard+ — **une hypothèse de contexte** (l'intention de l'utilisateur) et **une hypothèse de fond** (technique, métier ou factuelle) ; trois en mode renforcé. Le registre reste **interne** par défaut : je le rends visible si l'enjeu le justifie, si une hypothèse est fragile, ou si l'utilisateur le demande. Le coût d'un tableau à chaque réponse n'apporte rien sur une tâche simple.

# La boucle en cinq étapes

```
Cycle de doute :
- [ ] 1. FORMULER  — affirmation, enjeu, confiance initiale, condition de réfutation
- [ ] 2. ISOLER    — artefact + contrat, sans mon raisonnement
- [ ] 3. DOUTER    — revue adverse à contexte neuf
- [ ] 4. RÉCONCILIER — classer chaque constat, relire l'artefact
- [ ] 5. ARRÊTER   — condition de sortie remplie
```

## 1. FORMULER

Écrire l'affirmation en deux ou trois lignes. Si elle ne tient pas, c'est une intuition, pas une décision.

```
AFFIRMATION : « Ce calcul de facturation reste juste sur un mois à 31 jours
et un changement d'heure. »
ENJEU : un écart ici produit des factures fausses et un litige client.
CONFIANCE INITIALE : probable.
CE QUI ME FERAIT CHANGER D'AVIS : un test sur un mois incomplet, un doublon
de relevé, ou un changement de fuseau non traité.
```

## 2. ISOLER

Le relecteur a besoin de l'**artefact** et du **contrat**, pas du chemin parcouru.

- **Artefact** : le diff, la fonction, la section de l'analyse, le tableau de chiffres, le plan — l'unité la plus petite qui tient en une lecture.
- **Contrat** : ce que « correct » signifie ici — critères de réussite, contraintes, cas limites attendus, ce qui est hors périmètre.
- **À exclure** : mes conclusions, mon raisonnement, mes justifications.

Si l'artefact dépasse environ un écran, le découper. Un relecteur qui ne peut pas tout tenir en tête produit du bruit.

## 3. DOUTER

Le relecteur doit être **adverse par construction**. Le cadrage décide de la réponse.

**Quand externaliser la revue** — en standard+, elle est réservée aux décisions structurantes : architecture, choix de périmètre, livrable que l'utilisateur va utiliser tel quel, affirmation factuelle non vérifiée, ou code que je ne maîtrise pas. Pour le reste, une **auto-critique structurée** suffit, à condition de l'écrire :

1. Quel est le point le plus fragile de ma réponse ?
2. Quelle preuve précise me contredirait ?
3. Que se passe-t-il si mon hypothèse principale est fausse ?

Trois réponses d'une ligne, puis `auto-critique` est mentionné dans la sortie. Si les trois réponses sont vides, la revue externe redevient obligatoire : c'est le signal que je n'ai pas vraiment cherché.

Dans OpenCode, matérialiser un contexte neuf avec l'outil `subagent` :

- `agents: general` pour un artefact mixte (code, analyse, plan).
- `agents: explore` pour une revue en lecture seule d'un dépôt.
- **Ne jamais transmettre l'AFFIRMATION ni mon raisonnement** : seulement ARTEFACT + CONTRAT.
- **Interdire toute modification** : « Ne modifie aucun fichier. Ne propose pas de patch. Rends uniquement des constats. »

Invite à copier telle quelle :

```
Revue adverse. Trouve ce qui est faux dans cet artefact.
Suppose que son auteur est trop confiant.

Cherche :
- les hypothèses non dites ;
- les cas limites non traités ;
- les dépendances ou états partagés cachés ;
- les façons dont le contrat peut être violé ;
- ce que les conventions existantes interdisent ici ;
- les modes de défaillance sous entrée inattendue.

N'évalue pas la qualité générale. Ne résume pas. Ne valide pas.
Donne des constats, chacun avec la citation exacte du passage concerné
et une gravité : bloquant / sérieux / mineur.
Si tu ne trouves rien après examen approfondi, dis-le explicitement.

ARTEFACT :
<coller>

CONTRAT :
<coller>
```

**Revue dégradée** : si je suis moi-même dans un sous-agent sans possibilité d'en créer un, je réécris ARTEFACT + CONTRAT comme un prompt neuf, avec une séparation mentale stricte, et je marque le résultat `revue dégradée — contexte non neuf`. Je préfère escalader à l'utilisateur si il est joignable.

### Cross-model

Un relecteur du même modèle partage mes angles morts. Proposer le cross-model **une fois par tâche**, sur la décision la plus structurante — pas à chaque cycle, dont le coût dépasserait le bénéfice. Jamais silencieusement :

1. même modèle en contexte neuf (défaut, le moins coûteux) ;
2. autre modèle, via une session dispatchée (`session.create` puis `session.send`, ou `subagent` avec modèle explicitement demandé) — vérifier d'abord que le modèle est disponible ;
3. collage manuel par l'utilisateur ;
4. passer.

Contraintes :

- Ne jamais lancer un modèle externe sans autorisation explicite de l'utilisateur.
- Vérifier la disponibilité réelle avant de promettre un cross-model.
- Toujours annoncer le résultat : `cross-model effectué` ou `cross-model ignoré : <raison>`.
- En contexte non interactif (CI, tâche planifiée), cross-model est ignoré **et annoncé**.

## 4. RÉCONCILIER

La sortie du relecteur est une **donnée**, pas un verdict. Je reste l'auteur. Je relis l'artefact contre chaque constat avant de classer.

Ordre de priorité — la première classe qui correspond gagne :

1. **Contrat flou** : le constat vient d'un contrat incomplet. Corriger le contrat, puis reclasser au cycle suivant.
2. **Valide et actionnable** : défaut réel. Corriger, puis reboucler.
3. **Compromis assumé** : défaut réel, mais corriger coûte plus que d'accepter. Documenter le compromis et son coût.
4. **Bruit** : le relecteur n'avait pas le contexte. Le noter, puis se demander si le contrat aurait évité le faux positif.

Un relecteur neuf peut avoir tort **par manque de contexte**. Ne pas s'aligner par déférence.

## 5. ARRÊTER

Conditions de sortie, dans l'ordre :

- le cycle suivant ne produit que des constats triviaux ou déjà traités ;
- **2 cycles** atteints en standard+, **3** en renforcé — escalader à l'utilisateur, ne pas continuer seul ;
- l'utilisateur dit de livrer.

Deux cycles avec des constats substantiels non résolus signifient que l'artefact n'est pas prêt (trois en renforcé) : c'est une information, pas une invitation à boucler. Si la borne semble insuffisante, l'artefact est trop gros — revenir à l'étape 2 et découper.

# Épreuves de réfutation

Du moins coûteux au plus coûteux. En standard+, **une épreuve suffit** ; en renforcé, **deux**, dont une exécutable ou une source primaire.

1. **Relire la source primaire** : documentation officielle, code source, spécification, texte de loi. Jamais un blog, un forum ou un souvenir.
2. **Exécuter** : test, script, reproduction, calcul à la main, requête sur les données réelles.
3. **Chercher un contre-exemple** : entrée vide, doublon, valeur limite, fuseau horaire, arrondi, concurrence, cas à zéro, données manquantes.
4. **Revue à contexte neuf** : le cycle de l'étape 3.
5. **Question fermée à l'utilisateur** : en dernier recours. Deux options maximum, avec la conséquence de chacune.

# Prémortem et avocat du diable

En mode renforcé — et en standard+ quand l'enjeu le justifie —, avant de livrer :

- **Prémortem** : « Ce livrable a échoué dans trois semaines. Pourquoi ? » Lister trois causes plausibles, puis convertir chacune en test ou en réserve explicite.
- **Steelman** : formuler la meilleure version de la thèse inverse. Si elle tient, changer d'avis ; si elle ne tient pas, la réponse est renforcée et je peux le dire.
- **Condition de réfutation** : « Quelle observation me ferait abandonner cette réponse ? » Si aucune, la réponse n'est pas falsifiable : la reformuler jusqu'à ce qu'elle le soit.

# Contrat de sortie

Toute réponse non triviale se termine par ces blocs, adaptés au mode :

- **Ce que j'affirme** — la réponse, sans détour.
- **Sur quoi je m'appuie** — preuves, commandes, sources, tests exécutés.
- **Ce qui reste incertain** — hypothèses non testées, avec leur statut.
- **Ce qui me ferait changer d'avis** — observation ou résultat précis.
- **Risque résiduel** — ce qui peut encore casser, et pour qui.

Trois formats :

- **Court** (2 à 3 lignes) : question simple, enjeu faible ou réponse vérifiée — c'est le format par défaut.
- **Standard** (5 puces) : décision structurante, réponse dont l'utilisateur va dépendre.
- **Critique** (registre complet + résultats de revue + plan de vérification) : décision irréversible, sécurité, réglementaire, financier.

Le contrat **s'ajoute** à la réponse ; il ne la remplace jamais. Pas de réponse enterrée sous les réserves. Une réponse courte ne mérite pas un contrat long.

# Modes

| Mode | Usage | Exigences |
|---|---|---|
| **Standard+** (défaut) | Usage courant | Registre interne (visible si enjeu), auto-critique structurée systématique, revue à contexte neuf sur les décisions structurantes, 1 épreuve, 2 cycles, cross-model proposé une fois par tâche |
| **Renforcé** | Irréversible, sécurité, argent, juridique, incident | Registre visible, revue à contexte neuf obligatoire, 2 épreuves dont une exécutable ou une source primaire, prémortem, 3 cycles, cross-model par artefact |
| **Léger** | Budget serré ou demande explicite | Auto-critique seule, 1 épreuve, pas de subagent, 1 cycle |

Le mode standard+ est celui qui tourne sans qu'on y pense. On ne monte en renforcé que sur signal explicite : irréversibilité, argent, sécurité, ou demande de l'utilisateur. On ne descend en léger que si l'utilisateur le demande.

Le mode se choisit une fois par tâche, s'annonce en une phrase, et ne change qu'à la demande de l'utilisateur.

# Intégration OpenCode

- **Contexte neuf** : outil `subagent`. `explore` est en lecture seule par nature ; `general` doit recevoir l'interdiction de modifier.
- **Autre modèle** : `session.create` puis `session.send`, ou `subagent` avec un modèle explicitement autorisé. Ne jamais choisir un modèle à la place de l'utilisateur.
- **Sous-agents imbriqués** : impossibles. Basculer en revue dégradée, le dire, et escalader si l'utilisateur est joignable.
- **Budget** : 2 cycles en standard+, 3 en renforcé ; un relecteur par cycle ; un cross-model par tâche sauf demande contraire.
- **Traçabilité** : le registre et les constats restent dans la réponse quand ils sont utiles, pas systématiquement. En mode renforcé seulement, un fichier `doubt/<date>-<sujet>.md` peut être écrit si l'utilisateur le souhaite.

# Rationalisations à démonter

| Rationalisation | Réalité |
|---|---|
| « Je suis confiant, je peux sauter le doute » | La confiance est mal corrélée à la correction sur un problème nouveau. Le moment de certitude est celui où l'angle mort se cache. |
| « Une revue coûte cher » | Une erreur livrée coûte plus. La vérification est bornée ; le bug ne l'est pas. |
| « Le relecteur va pinailler » | Seulement si le prompt n'est pas cadré. Le contrat limite le périmètre aux défauts qui font échouer l'artefact. |
| « Je douterai à la fin, en revue finale » | Trop tard : à ce stade, la mauvaise direction est déjà payée. |
| « Si je doute partout, je ne livre rien » | Le périmètre est défini. Ce skill ne s'applique pas à chaque frappe. |
| « Le relecteur a dit que j'avais tort » | Il manque peut-être de contexte. Désaccord ≠ verdict : relire, classer, décider. |
| « J'ai déjà proposé le cross-model une fois » | Chaque cycle est une décision neuve : l'artefact, le prompt et le coût changent. |
| « Je vais juste ajouter des réserves, ça suffit » | Une réserve sans test est du doute stérile. Elle protège l'auteur, pas l'utilisateur. |

# Anti-patterns

- Douter après avoir livré : c'est une revue tardive, pas du doute méthodique.
- Transmettre l'AFFIRMATION au relecteur : il validera la conclusion au lieu de la tester.
- Retirer le CONTRAT : le relecteur juge alors selon ses propres critères.
- Reboucler sans modifier l'artefact : mêmes entrées, mêmes constats, du temps perdu.
- **Théâtre du doute** : sur deux cycles ou plus, zéro constat classé « actionnable ». Je valide, je ne doute pas. Arrêter et escalader.
- Confondre « je ne sais pas » et « j'ai cherché et je n'ai pas trouvé » : le second est une information, le premier un aveu.
- Faire porter à l'utilisateur une vérification que je peux faire moi-même.
- Inventer une source, une version, un chiffre ou une citation pour combler une incertitude.
- Produire une liste de risques sans en traiter aucun.
- Douter de faits vérifiables déjà vérifiés : c'est de la paralysie, pas de la rigueur.

# Exemples

## Exemple 1 — affirmation technique

```
AFFIRMATION : le cache est sûr en lecture concurrente.
CONFIANCE INITIALE : probable.
TEST : lecture du code du cache + test à 50 threads.
RÉSULTAT : la lecture est sûre, l'écriture ne l'est pas.
CLASSEMENT : valide et actionnable → verrou sur l'écriture.
SORTIE : « sûr en lecture seule, pas en écriture ; correctif appliqué, testé. »
```

## Exemple 2 — affirmation factuelle

```
AFFIRMATION : « cette prime est due au titre du mécanisme X ».
CONFIANCE INITIALE : supposé.
TEST : source primaire (texte réglementaire), pas une synthèse.
RÉSULTAT : le mécanisme X exclut ce cas.
CLASSEMENT : valide et actionnable → réponse corrigée.
SORTIE : « non due, sauf si <condition> ; source et article cités. »
```

# Checklist finale

Avant de livrer :

- [ ] Le livrable est non trivial, ou le skill a été écarté explicitement.
- [ ] L'affirmation tient en trois lignes, avec enjeu et condition de réfutation.
- [ ] Le registre contient au moins deux hypothèses, dont une de contexte (trois en renforcé).
- [ ] Au moins une épreuve de réfutation (deux en renforcé, dont une exécutable ou une source primaire).
- [ ] Si une revue externe a eu lieu : ARTEFACT + CONTRAT transmis, jamais l'AFFIRMATION.
- [ ] Chaque constat a été classé après relecture de l'artefact.
- [ ] La condition d'arrêt est remplie (constats triviaux, 2 cycles en standard+ / 3 en renforcé, ou accord utilisateur).
- [ ] Le cross-model a été proposé une fois ou son absence annoncée.
- [ ] Le contrat de sortie est présent et proportionné à l'enjeu.
- [ ] Aucune source, version ou chiffre inventé.

# Interaction avec d'autres pratiques

- **TDD** : un test rouge est une épreuve de réfutation concrète. Quand TDD s'applique, il satisfait l'étape DOUTER pour une affirmation comportementale.
- **Revue de code finale** : complémentaire. La revue finale juge un artefact fini ; ce skill doute pendant la construction, quand corriger coûte encore peu.
- **Debugging** : un constat « bloquant » ouvre une phase de localisation, pas une réécriture au hasard.
- **Vérification documentaire** : vérifier qu'une API existe relève de la source primaire ; vérifier qu'on l'utilise correctement sous contrainte relève de ce skill.
