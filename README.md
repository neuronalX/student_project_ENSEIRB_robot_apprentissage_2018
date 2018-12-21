

# Projets étudiants ENSEIRB option robot automne 2018
Projet étudiant pour le cours sur l'Apprentissage Artificiel de l'ENSEIRB/ENSC de Bordeaux.

Projets autour du reservoir computing avec l'utilisation de la classe ESN fournie par le dépôt [reservoirpy](https://github.com/neuronalX/reservoirpy) (c'est le dépôt [FunkyReservoir](https://github.com/neuronalX/FunkyReservoir) qui a été renommé).

Vous regarder ce [tutoriel jupyter notebook](https://github.com/neuronalX/Reservoir-Jupyter/blob/master/Minimal_ESN_-_FR.ipynb) pour vous aider. De façon général, vous pourrez trouver d'autres tutoriel et outils sur [ce repository](https://github.com/neuronalX/Reservoir-Jupyter).

## Généralités
### Nombre et tailles des groupes
Il y aura environ 6 groupes d'étudiants, avec pour chaque thème, 2 groupes d'étudiants pour ce thème.
Pour un même thème, les 2 groupes devront s'arranger entre eux pour ne pas travailler sur les mêmes corpus et ne pas explorer les mêmes choses.

### Pour tous les projets
- tester les performances des modèles selon le type de tâche soit:
  - (si le corpus est "plutôt petit" et appris en hors-ligne) avec une *cross-validation 10 fold* = on découpe le corpus en 10 *parts* égales, on utilise 9 parts pour entrainer et la 10e pour tester/valider les performances. Puis on fait de même pour toutes les parts et on moyenne le tout.
  - (si le corpus est "plutôt grand" et appris en-ligne) en découpant le corpus en deux parties : une partie pour l'apprentissage (plus grande), et une partie test/validation (plus petite) ; avec une répartition 70/30 par exemple.
  - si vous testez beaucoup d'*hyper-paramètres* (= paramètres non-appris) pour optimiser les performances de vos modèles, idéalement vous devrez séparer le corpus en 3, une pour l'**apprentissage**, une pour la **validation**, et une pour le **test** (*train/validation/test* en Anglais). Vous optimisez les performances de votre modèle en utilisant les ensemble d'apprentissage et de validation, et uniquement à la fin pour utiliser l'ensemble de test pour évaluer les performances "réelles de généralisation" de votre modèle (= sur des données sur lesquelles l'apprentissage n'a pas été optimisé pour).
  - Voici deux liens pour plus d'explications : [wikipedia](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets) [stats.stackexchange.com](https://stats.stackexchange.com/questions/19048/what-is-the-difference-between-test-set-and-validation-set)
- etudier l'effet des différents paramètres (ci-dessous) :
  - sur les performances,
  - et sur les "comportements" obtenus,
  - paramètres à étudier : nombre de neurones, rayon spectral (*spectral radius*) de la matrice récurrente W, mise à l'échelle de la matrice d'entée Win *input scaling*, "taux de fuite" des neurones (*leak-rate*), paramètre de régularisation (*ridge parameter*), pas d'apprentissage (*learning rate*) si vous utilisez un apprentissage en-ligne ;
  - (vous pouvez étudier d'autres paramètres en plus si vous le souhaitez).
- produire des fichiers de sortie (texte, son, image = spectrogramme) selon le projet
- si vous avez besoin d'apprendre sur de grands corpus (= sur un grand nombre de pas de temps) alos vous pourrez voir que l'apprentissage hors-ligne (*offline*) prendra un temps de plus en plus long (et pourra même "planter" à un moment car la matrice à inverser sera trop grande). Dans ce cas, l'apprentissage en-ligne (*online*) vous permettra d'apprendre des corpus beaucoup plus longs (grossièrement l'apprentissage sera linéaire par rapport aux nombres de pas de temps, contrairement à l'apprentissage hors-ligne). Mais selon la méthode d'apprentissage utiliser (LMS, RLS), cela nécessitera plusieurs *passes* sur le corpus (ou simplement un corpus plus grand si c'est un corpus généré).

### Choix des projets
Le choix du projet se fait par Pull-Request de ce projet ("repository"):
https://github.com/neuronalX/student_project_ENSEIRB_robot_apprentissage_2018

Il faut donc avoir un compte github, et faire une pull request pour éditer la liste ci-dessous (des sujets et des équipes) en ajoutant le nom de vos équipes et des membres de l'équipe.

Sujets / Equipes :
- 1. (TXT) - NOM EQUIPE : MEMBRES DE L'EQUIPE
  - Équipe 1.a : Thomas Fochesato - Jérémy Quintin - Zuzanna Muszynska
  - Équipe 1.b : Lauren Baillot - Merlin Boyer - Effie Segas
- 2. (MIDI) - NOM EQUIPE : MEMBRES DE L'EQUIPE
  - Équipe 2.a : Nina docteur - Kim cottrant - Gaëlle Lannuzel
  - Équipe 2.b : Fabien Monniot - Océane Bosseur - Vincent Leconte
- 3. (FREQ2WAV) - NOM EQUIPE : MEMBRES DE L'EQUIPE
  - Équipe 3.a : Hamza - Arthur - Florian
  - Équipe 3.b : Yann Besson - Alexis Juven - Romain Alverhne
- 4. (WAV2FREQ) - NOM EQUIPE : MEMBRES DE L'EQUIPE
  - Équipe 4.a : Jérémy Bezamat - Thomas Saliba - Yoann

### **(NEW)** Points BONUS
Si vous trouvez des *bugs* dans le code le [dépôt reservoirpy](https://github.com/neuronalX/reservoirpy) ou que vous proposez des améliorations par pull/request, vous obtiendrez des points bonus sur votre projet, étant donné que cela contribue à améliorer le code pour tous.

### **(NEW)** Rendu du projet
Le projet sera rendu début janvier (date communiquée plus tard).

Pour le rendu, vous devrez :
- créer et m'envoyer l'adresse d'un repository github (il peut être privé, mais vous devrez m'inviter pour que je puisse y accéder).
- écrire un rapport de 15 à 30 pages (tout inclus, page de garde, figures, bibliographie) décrivant votre travail et fournissant une discussion des résultats obenus et difficultés rencontrées. (N'incluez pas de code dans le rapport, sauf si c'est quelques lignes utiles pour vos explications et la compréhension.)

(Optionnel) Si vous préférez, vous pouvez faire un rapport sous forme jupyter notebook à la place du rapport "normal". Dans ce cas, il y aura de fait beaucoup plus de code "montré" que si c'était un rapport normal.

Après le rendu, vos projets pourront être référencé sur cette page, si vous le souhaitez.

## **(NEW)** FAQ
Le FAQ est mis à jour au fur et à mesure que vos questions par email. Pensez à venir le regarder régulièrement.

- "Concernant le sujet de traitement de texte, nous comprenons que nous devons faire apprendre le réseau avec un texte choisi, puis en entrant une certaine lettre, nous aurons des probabilités sur quelle sera la prochaine lettre du mot, est-ce correct ?"
  - *NB: dans une certaine mesure les réponses pour la tâche TXT sont aussi valables pour la tâche MIDI*

    Concernant le sujet de traitement de texte, oui l'idée est de prédire la distribution des prochains caractères.

    L'idée est de faire qqch similaire à ce qui est décrit dans ce blog : https://karpathy.github.io/2015/05/21/rnn-effectiveness/ mais en utilisant des corpus plus petit bien sûr.

    Vous pouvez vous inspirer (et donc améliorer) tout en utilisant la classe ESN de https://github.com/neuronalX/reservoirpy le code qui se trouve ici : regardez le fichier *Word_Generator2.py* dans ce repository https://github.com/neuronalX/Reservoir-Jupyter

    Une amélioration à faire est par exemple d'utiliser une *fonction de coût* (*cost function*) qui sera plus adaptée que les moindres carrés, en utilisant la *cross-entropy* qui permet de comparer deux distributions (les ditributions des prochains caractères) plutôt que de calculer la distance euclidienne entre deux vecteurs.

- "Nous ne comprenons pas ce qu'il faut fournir au réseau de neurones en sortie pour un entrainement supervisé ayant en entrée uniquement des fichiers MIDI. Pouvez vous nous orienter sur le sujet ? "

    Comme pour le projet de prédiction/génération de texte (où il s'agit de prédire/générer le prochain caractère), il s'agit de prédire/générer la prochaine note (durée et hauteur).
    A chaque pas de temps le réseau doit prédire la prochaine note.

    Le problème peut être séparé en deux pour hauteur et la durée (prédire uniquement la hauteur, ou uniquement la durée) dans un premier temps afin de simplifier le problème. Ensuite, les deux pourront être fait ensemble (avec un seul ou deux réservoirs).

## Sujets proposés à choisir

### 1. (TXT) Prédiction et génération de texte
- prendre un corpus : ex: petit chaperon rouge
- coder une tâche de prédiction et de génération de texte, caractère par caratère
  - avec un softMax en sortie, et un choix probabiliste pour ne pas générer tout le temps les mêmes suites de caractères
  - les fonctions de cout potentiellement intéressante (cross-entropy, etc.)
- quels sont les effets d'avoir différents corpus, de différentes tailles, avec des vocabulaire différents ?
- *NB: dans une certaine mesure les tâches TXT et MIDI ont des points communs, sachez les exploiter.*

### 2. (MIDI) Prédiction et génération de fichier midi
- prendre un corpus de fichiers midi d'un certain style (Bach, Mozart, jazz, ...) avec un seul instrument (une seule ligne mélodique) où une seule note est jouée à la fois (c'est à dire pas d'accords)
- coder une tâche de prédiction et une tâche de génération de musique sous la même forme qu'un fichier midi (c'est à dire une séquence de nombre entiers correspondants à différentes notes et durées)
- la tâche peut être séparé en deux sous-taches dans un premier temps:
  - prédiction/génération simplement sur la hauteur des notes (pitch)
  - prédiction/génération simplement sur la durée des notes (rythmique)
- softmax (idem que pour projet sur le texte)
- produire le fichier midi, et utiliser une bibliothèque pour automatiquement produire la musique générée
- *NB: dans une certaine mesure les tâches TXT et MIDI ont des points communs, sachez les exploiter.*

### 3. (FREQ2WAV) Transformation de frequences en ondes sonores
- générer un corpus avec toutes les notes d'un piano qui vont générer les fréquences correspondant aux différentes touches
  - puis faire des enchainements croissant, décroissant et aléatoires de ces différentes fréquences
- la tâche peut être faite avec des niveaux de difficulté croissante
  - d'abord apprendre à générer des ondes (= signal prériodique) pour une seule octave
  - puis augmenter jusqu'au nombre d'octaves maximums que le reservoir semble pouvoir apprendre
- générer les fichiers .json et .numpy contenant les vecteurs d'ondes correspondantes
- utiliser une bibliothèque pour générer le son correspondant à ces vecteurs d'ondes
- générer également les images des spectrogrammes correspondant aux sons générés
- sur la [page d'introduction des ESN de Scholarpedia](http://www.scholarpedia.org/article/Echo_state_network) vous pourrez trouver l'exemple de cette tâche.
  - Image provenant de www.scholarpedia.org/article/Echo_state_network (CC BY-NC-SA 3.0) : ![Figure 1: The basic schema of an ESN, illustrated with a tuneable frequency generator task. Solid arrows indicate fixed, random connections; dotted arrows trainable connections.](http://www.scholarpedia.org/w/images/thumb/c/c6/FreqGenSchema.png/500px-FreqGenSchema.png)

### 4. (WAV2FREQ) Transformation d'ondes en fréquences
- ce projet correspond à faire "l'inverse" du projet 3. (FREQ2WAV)
- c'est-à-dire que vous devez prendre en entrée un signal périodique en entrée, et fournir la fréquence de ce signal en sortie.
