# Laboratoire 1 — Gestion de versions et travail d'équipe

**Cours :** 6GEI311 — Architecture des logiciels
**Étudiant :** Zongo Julien
**Coéquipier :** Abdoul Razack Zongo
**Date :** 11 septembre 2026

## 1. Résumé de ce que j'ai appris 
Ce laboratoire m'a fait passer d'un usage mécanique de Git à une compréhension
de son modèle de fonctionnement. Git et GitHub ensemble est la meilleure arme pour moi  en tant que dev.
Un fichier traverse le répertoire de travail, l'index
(*staging*) puis le dépôt local avant d'atteindre le dépôt distant. `add`,
`commit` et `push` sont trois opérations distinctes, et non trois étapes d'une
même action. J'ai passé du temps à répéter `git commit` sur un `git add` sans
effet avant de comprendre que `nothing to commit` était une information exacte
et non une erreur. Il est possible de revenir en arrière souvent quand les changements sont encore locaux.


### Partie 2 situation 2

## 3. Retour d'expérience — description et lecture d'une issue
Une issue, c'est un billet de signalement : tu ouvres une fiche pour dire « il y a un problème ici », et elle reste ouverte tant que personne ne l'a réglé. On peut l'assigner à un membre de l'équipe.
On peut dire que c'est la formalisation écrite d'une demande de maintenance corrective.
Sa qualité conditionne le temps que le destinataire mettra à reproduire, puis à
localiser le problème. Elle doit donc respecter une certaine structure : 

### Ce qu'une description doit contenir

1. **Un titre spécifique** — il doit identifier le problème à lui seul, dans
   une liste de cinquante issues. « Ligne "erreur injectée" indésirable dans
   `Dossier_A/textA.txt` » plutôt que « bug dans un fichier ».
2. **La localisation** — fichier, branche, identifiant de commit, auteur,
   date. C'est ce qui permet au destinataire de partir directement du bon
   endroit.
3. **Le comportement attendu** et **le comportement observé**, séparément.
   L'écart entre les deux *est* le problème ; l'énoncer ainsi évite les
   interprétations.
4. **Les étapes de reproduction**, numérotées, exécutables telles quelles par
   quelqu'un qui ne connaît pas le contexte.
5. **L'impact** — ce que le défaut empêche ou dégrade. C'est ce qui permet de
   prioriser.

### Comment elle doit être structurée

En sections courtes et titrées, du général au particulier : description,
localisation, attendu, observé, reproduction, impact. Le lecteur doit pouvoir
s'arrêter après trois lignes s'il a déjà compris, ou descendre jusqu'aux
étapes de reproduction s'il ne voit pas le problème.

Le test à appliquer avant de publier : *si je recevais cette issue sans
contexte, dans six mois, sur un projet de cinquante mille lignes, pourrais-je
localiser le problème sans poser une seule question de retour ?*

### Sur la lecture et la réponse

Une réponse utile cite des identifiants, pas des impressions. À l'étape 10, le
membre B doit désigner le commit problématique et la dernière version
fonctionnelle par leur SHA : sur GitHub, un identifiant écrit dans un
commentaire devient un lien vers le commit correspondant.

Deux limites observées pendant ce laboratoire méritent d'être notées.

D'abord, **une issue ne vaut que par la stabilité de ce qu'elle référence**.
Après un `push --force`, l'issue ouverte à l'étape 9 pointait vers un commit
qui n'existait plus : la description restait lisible, mais la preuve avait
disparu.

Ensuite, **la qualité des messages de commit conditionne la lecture de
l'issue**. À deux reprises, un message désignait le mauvais fichier, ce qui a
conduit à cibler le mauvais commit lors d'un revert. L'issue et l'historique
forment un ensemble : documenter l'un sans soigner l'autre ne suffit pas.

Enfin, la revue porte sur l'artefact, jamais sur la personne. Une issue décrit
un écart entre un état attendu et un état observé — c'est ce qui permet à
l'équipe de signaler ses propres erreurs sans coût social, condition de la
qualité sur la durée.
