<p align="center"><img width="600"src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*SK4JGjtWs9BsfGGXOrnnig.png"/><p>

# À propos de Gitflow

Git-Flow est un modèle de _branching_ alternatif rattaché à Git, cad qu'il offre des commandes alternatives à celle de Git pour créer, modifier, et merge des branches, permettant un workflow different.

## Differences avec le Workflow Git

Git-Flow est optimisé pour un dévelopement sur modèle de "release", où des changements multiples sont déployés par packs périodiques sur l'application.

Git-Flow crée automatiquement une branche **develop** qui sert de branche de travail. La branche **main** reste ainsi stable pour l'utilisateur malgré les changements sur lesquels les devs travaillent.

![main&dev](/images/git-flow-1.png)

A partir de cette branche **develop**, les devs peuvent créer en local des branches de **feature** pour travailler sur chaque nouvelle fonctionnalité en parrallèle. Chaque **feature** terminée et validée est ensuite merge sur la branche **develop**.

![feature](/images/git-flow-2.png)

Pour pouvoir modifier la branche **main** auquel l'utilisateur à accès, les devs passent par une branche **release** qui communique les changements de la branche **develop**, et les merge à la **main**.

![release](/images/git-flow-3.png)

Lors d'une détection de bugs, les branches **hotfix**, naissant de la branche **main** permettent de les résoudre, et ces changements s'appliquent simultanément aux la branche **main** et **develop**. Ainsi, l'apparition de bugs n'interromp pas le travail des different collaborateurs.

![hotfix](/images/git-flow-4.png)
