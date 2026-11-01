# Transcription complète — N8N_video.mp4

Durée de la vidéo : 00:08:50
Langue parlée : français
Intervenant audible : Antonin (identifié par son introduction à 00:00.5)

Note : transcription fidèle issue de l'audio ; les hésitations, répétitions et phrases interrompues sont conservées lorsqu'elles sont audibles.

[00:00.5 - 00:02.3] [Antonin] Hello Lucas, c'est Antonin.
[00:02.3 - 00:12.6] [Antonin] Euh, bah aujourd'hui, je vais te présenter mon workflow que j'ai construit au cours de la semaine, euh, qu'on a eue avec toi et que j'ai continué,
[00:12.6 - 00:16.8] [Antonin] euh, de travailler de mon côté parce que c'est vraiment quelque chose qui m'a plu.
[00:16.8 - 00:24.4] [Antonin] Euh, là, j'ai automatisé, du coup, dans c-- dans-- pour, euh, pour mon projet, une page web de suivi de musculation, en fait.
[00:24.4 - 00:32.8] [Antonin] Comme je fais pas mal de sport, euh, bah, c'est toujours la galère un peu de noter ses séries et tout sur, euh, sur l'appli de notes, sur le téléphone et tout.
[00:32.8 - 00:35.4] [Antonin] Donc là, en fait, j'ai vraiment, euh...
[00:35.4 - 00:41.4] [Antonin] Donc là, en fait, j'ai vraiment un workflow qui tient uniquement sur N8N.
[00:41.4 - 00:44.0] [Antonin] En fait, c'est N8N qui fait tourner la page web, vraiment.
[00:44.0 - 00:54.0] [Antonin] Euh, la première étape, c'est une étape d'initialisation avec la création de deux tables, une table qui liste tous mes exercices de chaque séance, euh, qu'il y a au c-- au c-- dans la s-- dans
[00:54.0 - 01:02.4] [Antonin] la semaine et une deuxième table qui répertorie tous les exercices faits pour les stocker, en fait, et qui m'aide pour me donner des conseils.
[01:02.4 - 01:12.7] [Antonin] Donc, euh, après, la deuxième étape, mais moi, je considère que c'est la première, c'est l'affichage de l'app, en fait, qui lit l'historique, euh, et le programme, qui calcule la cible type,
[01:12.7 - 01:20.2] [Antonin] euh, de séries à faire durant la séance, euh, et qui, qui renvoie la page web tout simplement.
[01:20.2 - 01:26.0] [Antonin] Après, on a la, la, la-- le troisième-- euh, la troisième étape : enregistrer, euh, une séance.
[01:26.0 - 01:30.8] [Antonin] En fait, enregistrer une séance, ça reçoit les séries, euh, les écrit dans la table euh...
[01:30.8 - 01:35.9] [Antonin] dédiée, puis envoie une confirmation, en fait, euh, à la fin de l'enregistrement.
[01:35.9 - 01:40.1] [Antonin] Tout ça, je vais leur montrer, euh, un peu, euh, dans le, ben, Enregistrer séance.
[01:40.1 - 01:43.1] [Antonin] Je vais le montrer, c'est là, en fait, euh, dans Séance.
[01:43.1 - 01:47.0] [Antonin] Une fois qu'on a tout noté, hop, enregistrer la séance.
[01:47.0 - 01:49.5] [Antonin] Ça vient stocker directement dans la bonne table.
[01:49.5 - 01:57.4] [Antonin] On a, euh, le truc, euh, la partie bilan hebdomadaire que je présenterai, l'analyse du coach où là, il y a mon nœud Gemini, en fait.
[01:57.4 - 01:59.7] [Antonin] Bah, c'était tout en dessous.
[01:59.7 - 02:01.1] [Antonin] Euh, hop là.
[02:01.1 - 02:01.8] [Antonin] Voilà.
[02:01.8 - 02:02.8] [Antonin] Analyser ma séance.
[02:02.8 - 02:08.4] [Antonin] Si je remplis tout, bah, le-- j'ai un petit coach, en fait, qui me dit si ma séance allait bien, si ça manque d'intensité et tout.
[02:08.4 - 02:14.7] [Antonin] C'est encore un peu à améliorer, mais bon, comme fallait inclure un nœud G-- un, un, un nœud, pardon, Gemini, je l'ai mis là.
[02:14.7 - 02:18.4] [Antonin] Euh, il y a aussi beaucoup de, de code nodes.
[02:18.4 - 02:26.0] [Antonin] Je sais que t'étais pas trop fan, mais en fait, je voyais pas comment faire d'autre, euh, pour faire af-afficher comme je voulais sur, euh, sur la page web.
[02:26.0 - 02:26.9] [Antonin] Je te montrerai après.
[02:26.9 - 02:36.9] [Antonin] Euh, après, on récupère une API par une API, donc API, euh, de, d'un, d'une appli, d'un site web, euh, de sport, en fait,
[02:36.9 - 02:46.9] [Antonin] qui vient me, me les-- faire toute une liste d'exercices, euh, avec nom, euh, et une photo de l'exercice, en fait, euh, pour mieux me repérer
[02:46.9 - 02:48.3] [Antonin] moi quand je fais mes exercices.
[02:48.3 - 02:58.8] [Antonin] Et après, ben, tout simplement pour configurer mes ex-- mes séances, ben ajouter au, un, un, un-- au programme une séance, ajouter un exercice, le modifier
[02:58.8 - 02:59.7] [Antonin] ou bien le supprimer.
[02:59.7 - 03:07.8] [Antonin] Donc, euh, ben là, je vais te montrer en fait comment ça se présente sur ma page web, euh, qui se décompose en quatre, euh, p'tits, p'tites sous-pages.
[03:07.8 - 03:12.8] [Antonin] Donc la page accueil, en fait, ben, avec, ben, le bilan hebdomadaire que je parlais, euh, avant.
[03:12.8 - 03:17.4] [Antonin] Donc en fait, de cette semaine, j'ai fait mais que trois séances sur les cinq que j'avais prévues.
[03:17.4 - 03:24.1] [Antonin] Euh, le total des séances faites, euh, depuis que, ben, je stocke tout ça sur, euh, sur mon workflow N8N dans les data tables.
[03:24.1 - 03:28.4] [Antonin] Euh, mes cinq séances, euh, type.
[03:28.4 - 03:30.3] [Antonin] Ça, il faut pas faire attention.
[03:30.3 - 03:32.8] [Antonin] Les cinq séances type, euh, que je fais.
[03:32.8 - 03:35.4] [Antonin] Et donc là, ben, en fait, on peut aussi passer par là.
[03:35.4 - 03:43.1] [Antonin] Si je lance une séance, et ben pour enregistrer, imaginons que je vais faire une séance, euh, ben, pec triceps.
[03:43.1 - 03:46.9] [Antonin] Euh, on met la date, euh, de la séance.
[03:46.9 - 03:48.8] [Antonin] J'ai un petit minuteur de repos, en fait.
[03:48.8 - 03:56.8] [Antonin] C'est, c'est-- le jour, euh, où en fait, ben, j'aurai cette app acc-- euh, 'fin, ce, cette page web accessible, euh, sur mon téléphone.
[03:56.8 - 03:59.1] [Antonin] Pour ça, il faut que je stocke tout ça chez un VPS.
[03:59.1 - 04:00.2] [Antonin] On en reparlera un peu à la fin.
[04:00.2 - 04:06.3] [Antonin] Euh, j'ai mis un petit minuteur, en fait, qui me permet de bien timer mon temps de repos entre chaque exercice.
[04:06.3 - 04:07.4] [Antonin] Et donc voilà.
[04:07.4 - 04:17.4] [Antonin] Ben, en fait, là, ça a répertorié mes six ex-- six exercices pour la séance pec triceps avec l'exercice, la photo de l'exercice, les, les petits poids utilisés
[04:17.4 - 04:26.0] [Antonin] sur la dernière séance et le petit conseil, euh : maintien du poids, là, donc faire huit, huit reps sur ch-chaque série.
[04:26.0 - 04:29.1] [Antonin] Voilà, avec une petite note fati-- facultative.
[04:29.1 - 04:32.2] [Antonin] Donc là, on a tous mes exercices pour le haut du corps.
[04:32.2 - 04:35.3] [Antonin] Là, on a les trois exercices pour les triceps.
[04:35.3 - 04:42.3] [Antonin] Et, et comme ça, ça permet de, d'enregistrer mes séances et de, euh, de les histori-- euh, faire un historique plus facilement.
[04:42.3 - 04:50.3] [Antonin] Donc là, juste la petite page, euh, programme, en fait, où, ben, mes-- c'est mes exercices de chaque séance, en fait, que j'ai prédéfinis.
[04:50.3 - 04:52.9] [Antonin] Et comme ça, je-- après, je les ai ici.
[04:52.9 - 04:54.7] [Antonin] Après, du coup, on a la page historique.
[04:54.7 - 05:03.2] [Antonin] Là, ça va être le, le, le gros point positif, en fait, où je vais pouvoir suivre, ben, l'évolution du poids que je prends, euh, sur chaque exercice.
[05:03.2 - 05:08.1] [Antonin] Là, c'est pas révélateur parce que y a-- j'ai fait peu de séances encore, euh, avec ça.
[05:08.1 - 05:13.5] [Antonin] Donc, euh, ben, en fait, ben là, on peut voir qu'il y a pas de séance, donc je peux pas voir, mais on va rester sur...
[05:13.5 - 05:16.9] [Antonin] Euh, ben, par là, par exemple, j'ai dégraissé.
[05:16.9 - 05:21.2] [Antonin] Il y a une séance où je, je devais pas avoir envie, mais là, on peut avoir une, une progression.
[05:21.2 - 05:26.4] [Antonin] Donc après, ça sera encore des petits trucs à améliorer, euh, ben, sur, euh, le petit conseil, en fait.
[05:26.4 - 05:29.0] [Antonin] Euh, peut-être faire un prorata et tout.
[05:29.0 - 05:37.3] [Antonin] Donc, il y a beaucoup de choses à améliorer, mais déjà, ben, en fait, euh, ce workflow, il m'aide énormément, euh, au quotidien.
[05:37.3 - 05:42.6] [Antonin] Donc maintenant, on va voir les commandes, euh, commandes à faire depuis le terminal.
[05:42.6 - 05:47.1] [Antonin] Donc là, j'avais déjà fait-- prédéfini une petite commande.
[05:47.1 - 05:50.1] [Antonin] Donc là, c'est la commande n8n-cli-env-local...
[05:50.1 - 05:51.5] [Antonin] nanana.
[05:51.5 - 06:01.7] [Antonin] Donc en fait, cette commande, euh, elle confirme que le fichier que je, que je montrais, euh, ben, là, mon workflow avant sur la page N8N, c'est exactement le même workflow qui tourne s-- en local sur mon PC.
[06:01.7 - 06:08.7] [Antonin] Donc là, on peut l'avancer et normalement, ça devrait apparaître un « Identique » euh, pour, euh...
[06:08.7 - 06:13.9] [Antonin] Pour tout simplement comparer les deux fichiers.
[06:13.9 - 06:15.5] [Antonin] Et voilà.
[06:15.5 - 06:18.9] [Antonin] Donc on peut voir effectivement que le fichier est identique.
[06:18.9 - 06:21.8] [Antonin] Euh, là, je vais prendre juste la deuxième commande.
[06:21.8 - 06:28.9] [Antonin] Je n'ai pas-- je ne fais pas les commandes push, unit et ça, parce que, en fait, je ne suis pas très à l'aise.
[06:28.9 - 06:34.5] [Antonin] Comme tout est en local sur mon ordinateur, je n'ai pas envie de, de faire n'importe quoi avec mes fichiers.
[06:34.5 - 06:44.5] [Antonin] Donc là, j'ai pris une deuxième touche, euh, qui, en fait, elle, vérifie que le fichier respecte la syntaxe et la structure attendue par N8n.
[06:44.5 - 06:48.1] [Antonin] Euh, si tout est correct, normalement, il devrait afficher Valid.
[06:48.1 - 06:49.2] [Antonin] Voilà, Valid.
[06:49.2 - 06:53.5] [Antonin] Donc là, on peut voir que mon workflow est valide, tout tourne bien.
[06:53.5 - 07:03.7] [Antonin] Euh, donc, bah, pour faire un petit feedback un peu sur, sur mon, mon projet, j'ai mis du temps à le trouver, mais en fait, bah, ça va me servir au quotidien.
[07:03.7 - 07:08.0] [Antonin] Comme il enregistre mes séries, mes séances, il me dit quelle, quelle charge utiliser.
[07:08.0 - 07:15.1] [Antonin] C'est-- Ça va être un, un, un bon entraînement pour moi, en fait, pour essayer de, ben, d'améliorer tout ça.
[07:15.1 - 07:23.1] [Antonin] Euh, donc, ben, il y a beaucoup de nœuds de code, comme tu pouvais voir sur, sur mon, sur mon workflow, mais je voyais pas comment faire.
[07:23.1 - 07:29.4] [Antonin] En fait, c'est pour, ben, vraiment la-- appliquer les règles que je voulais et à faire afficher tout ce que je voulais.
[07:29.4 - 07:30.3] [Antonin] Il y en avait besoin.
[07:30.3 - 07:40.5] [Antonin] Euh, donc je pense qu'il y avait des moyens d'améliorer, peut-être d'en supprimer quelques-uns, mais je ne voyais pas comment mieux faire que ça, parce que c'était un peu plus simple que mon projet
[07:40.5 - 07:41.0] [Antonin] de base.
[07:41.0 - 07:44.6] [Antonin] Euh, en fait, je construisais pas une page Web, etc.
[07:44.6 - 07:55.5] [Antonin] Donc, ben, la prochaine étape, c'est tout simplement d'héber-, d'héberger mon N8n sur un VPS, parce que, ben, là, en fait, mon N8n, il tourne sur Docker
[07:55.5 - 08:05.5] [Antonin] en local, mais j'aimerais bien faire tourner mon, mon workflow sur un VPS pour pouvoir a-accéder à la page, euh, ben, tout simplement sur mon téléphone
[08:05.5 - 08:07.8] [Antonin] quand je suis directement à la salle de sport.
[08:07.8 - 08:12.5] [Antonin] Euh, et puis, si je devais faire un petit feedback sur le cours, moi, j'ai beaucoup aimé.
[08:12.5 - 08:14.1] [Antonin] Je connaissais pas du tout N8n.
[08:14.1 - 08:17.4] [Antonin] Euh, ça m'a un peu ouvert l'esprit.
[08:17.4 - 08:22.2] [Antonin] En fait, ben, des fois, maintenant, je pense à des petits trucs à automatiser.
[08:22.2 - 08:31.2] [Antonin] C'est pour ça que je pense à prendre un VPS pour pouvoir stocker plein de petites solutions que je fais, euh, que ce soit pour moi, ma famille ou mes proches.
[08:31.2 - 08:39.9] [Antonin] Euh, en fait, maintenant, c'est d'imaginer et préparer bien, bien l'architecture, la règle du dix, quatre-vingt, dix qu'on a vue en cours.
[08:39.9 - 08:42.5] [Antonin] Donc moi, franchement, j'ai trop aimé ton cours.
[08:42.5 - 08:44.1] [Antonin] Euh, voilà.
[08:44.1 - 08:48.5] [Antonin] Merci pour tout et j'espère que tu auras bien aimé mon petit projet.
