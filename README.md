

# Projets étudiants ENSEIRB option robot automne 2018
Projet étudiant pour le cours sur l'Apprentissage Artificiel de l'ENSEIRB/ENSC de Bordeaux.

Projets autour du reservoir computing avec l'utilisation de la classe ESN fournie par le repository [FunkyReservoir](https://github.com/neuronalX/FunkyReservoir).

## Généralités
### Nombre et tailles des groupes
Il y aura environ 6 groupes d'étudiants, avec pour chaque thème, 2 groupes d'étudiants pour ce thème.
Pour un même thème, les 2 groupes devront s'arranger entre eux pour ne pas travailler sur les mêmes corpus et ne pas explorer les mêmes choses.

### Pour tous les projets
- tester les performances des modèles en cross-validation 10 fold
- etudier l'effet de différents paramètres (nombre de neurones, rayon spectral, input scaling, leak-rate, ...)
  - sur les performances et comportements obtenus
- produire des fichiers de sortie (texte, son, image = spectrogramme) selon le projet

### Choix des projets
Le choix du projet se fait par Pull-Request de ce projet ("repository"):
https://github.com/neuronalX/student_project_ENSEIRB_robot_apprentissage_2018

Il faut donc avoir un compte github, et faire une pull request pour éditer la liste ci-dessous (des sujets et des équipes) en ajoutant le nom de vos équipes et des membres de l'équipe.

Sujets / Equipes :
- 1. (TXT) - NOM EQUIPE - MEMBRES DE L'EQUIPE
- 2. (MIDI) - NOM EQUIPE - MEMBRES DE L'EQUIPE
- 3. (FREQ2WAV) - NOM EQUIPE - MEMBRES DE L'EQUIPE
- 4. (WAV2FREQ) - NOM EQUIPE - MEMBRES DE L'EQUIPE

## Sujets proposés à choisir

### 1. (TXT) Prédiction et génération de texte
- prendre un corpus : ex: petit chaperon rouge
- coder une tâche de prédiction et de génération de texte, caractère par caratère
  - avec un softMax en sortie, et un choix probabiliste pour ne pas générer tout le temps les mêmes suites de caractères
  - les fonctions de cout potentiellement intéressante (cross-entropy, etc.)
- quels sont les effets d'avoir différents corpus, de différentes tailles, avec des vocabulaire différents ?

### 2. (MIDI) Prédiction et génération de fichier midi
- prendre un corpus de fichiers midi d'un certain style (Bach, Mozart, jazz, ...) avec un seul instrument (une seule ligne mélodique) où une seule note est jouée à la fois (c'est à dire pas d'accords)
- coder une tâche de prédiction et une tâche de génération de musique sous la même forme qu'un fichier midi (c'est à dire une séquence de nombre entiers correspondants à différentes notes et durées)
- la tâche peut être séparé en deux sous-taches dans un premier temps:
  - prédiction/génération simplement sur la hauteur des notes (pitch)
  - prédiction/génération simplement sur la durée des notes (rythmique)
- softmax (idem que pour projet sur le texte)
- produire le fichier midi, et utiliser une bibliothèque pour automatiquement produire la musique générée

### 3. (FREQ2WAV) Transformation de frequences en ondes sonores
- générer un corpus avec toutes les notes d'un piano qui vont générer les fréquences correspondant aux différentes touches
  - puis faire des enchainements croissant, décroissant et aléatoires de ces différentes fréquences
- la tâche peut être faite avec des niveaux de difficulté croissante
  - d'abord apprendre à générer des ondes pour une seule octave
  - puis augmenter jusqu'au nombre d'octaves maximums que le reservoir semble pouvoir apprendre
- générer les fichiers .json et .numpy contenant les vecteurs d'ondes correspondantes
- utiliser une bibliothèque pour générer le son correspondant à ces vecteurs d'ondes
- générer également les images des spectrogrammes correspondant aux sons générés

### 4. (WAV2FREQ) Transformation d'ondes en fréquences
- ce projet correspond à faire "l'inverse" du projet 3. (FREQ2WAV)
