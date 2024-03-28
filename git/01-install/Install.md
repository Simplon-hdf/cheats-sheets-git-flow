![Logo git](https://git-scm.com/images/logos/1color-lightbg@2x.png)

# Introduction

- Git est un système de contrôle de version largement utilisé aujourd’hui. Il a été initialement développé en 2005 par Linus Torvalds, le créateur du noyau du système d’exploitation Linux. De nombreux projets logiciels, qu’ils soient commerciaux ou open source, reposent sur Git pour le contrôle de version.

# Qu’est-ce que Git ?

- Git est un système de contrôle de version décentralisé. Contrairement aux systèmes de contrôle de version plus anciens comme CVS ou Subversion, où l’historique complet des versions est stocké en un seul emplacement, Git fonctionne de manière décentralisée. Chaque copie de travail du code est également un dépôt qui contient l’historique complet de tous les changements.

Les trois objectifs clés de Git sont les suivants :

- ___Performances___ : Git est optimisé pour des actions telles que les commits, les branches, les fusions et les comparaisons de versions. Ses algorithmes exploitent une connaissance approfondie des attributs courants des arborescences de fichiers de code source réel.
Sécurité : Git se concentre sur le contenu des fichiers plutôt que sur leurs noms, ce qui le rend plus robuste face aux renommages fréquents.

- ___Collaboration___ : Git permet de travailler avec d’autres utilisateurs à l’aide de branches, de branches, de branches, de branches, de branches. Il permet également de travailler en équipe sur des projets à plusieurs développeurs.

- ___Flexibilité___ : Git s’adapte à divers environnements de développement et systèmes d’exploitation.

En résumé, Git est un outil puissant pour gérer l’historique des versions de votre code, collaborer avec d’autres développeurs et suivre les modifications au fil du temps. Que vous soyez un débutant ou un expert, Git est essentiel pour tout projet de développement logiciel

# Comment installer git ?

Pour installer Git sur votre ordinateur, voici les étapes à suivre en fonction de votre système d’exploitation :

Linux :

- Si vous utilisez une distribution basée sur Fedora (ou toute distribution parente basée sur RPM comme RHEL ou CentOS), vous pouvez installer Git avec la commande :

````
sudo dnf install git-all
````

Pour une distribution basée sur Debian (comme Ubuntu), utilisez la commande :

````
sudo apt install git-all
````

Pour plus d’options et d’instructions d’installation sur différentes versions Unix, consultez le site web de Git.

macOS :

- La méthode la plus simple est d’installer les Xcode Command Line Tools. Sur Mavericks (10.9) ou une version ultérieure, ouvrez le terminal et exécutez :

````
git --version
````

- S’il n’est pas déjà installé, il vous demandera de le faire.
Vous pouvez également télécharger l’installateur binaire depuis le site web de Git ou l’installer via GitHub [for macOS.](https://git-scm.com/download/mac)

Windows :

- [Téléchargez l’application officielle depuis le site web de Git.](https://git-scm.com/downloads)

- [Git Desktop](https://git-scm.com/downloads) : Cet outil est une version desktop qui permet de suivre l’historique des versions de code. Il est aussi une interface graphique pour Git Desktop.

- [Git Bash](https://git-scm.com/downloads) : Git Bash est une interface de ligne de commande qui permet de suivre l’historique des versions de code. Il est aussi une interface graphique pour Git Bash.

- [Git for Windows](https://git-scm.com/downloads) : Git for Windows est une interface de ligne de commande qui permet de suivre l’historique des versions de code. Il est aussi une interface graphique pour Git for Windows.

Vous pouvez également utiliser le paquet Chocolatey Git pour une installation automatisée.
Une autre option est d’installer GitHub for Windows, qui inclut une version en ligne de commande avec une interface graphique.
N’hésitez pas à choisir la méthode qui convient le mieux à votre système et à vos préférences ! 🚀

- plus d'informations complémentaires sur git et giflow :

https://gamma.app/docs/Quest-ce-que-Git-Flow--th2885p6wv1rnfv?mode=present#card-rssnx5gejir56aw

- une petite video de 5 min pour comprendre git...

https://youtu.be/gGKZLfPYORs?si=5ErR7YGKXLe5HRxX

![Logo gitflow](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*SK4JGjtWs9BsfGGXOrnnig.png)
----
----

# Introduction

- GitFlow est un modèle de gestion des branches Git qui facilite l’organisation du cycle de développement d’un projet. Voici comment l’installer et l’utiliser :

# Installation 

- Pour installer GitFlow, vous devez d’abord vous assurer que Git est déjà installé sur votre système.

- Ensuite, installez le plugin GitFlow. Voici quelques options :

Sur macOS :

- Utilisez Homebrew :

````
brew install git-flow-avh
````

Ou avec Macports :

````
port install git-flow-avh
````

Sur Windows :

- Utilisez [GitFlow pour Windows](https://github.com/nvie/gitflow/wiki/Windows)

- Utilisez GitFlow pour [Windows avec Git Bash](https://github.com/nvie/gitflow/wiki/Windows-Git-Bash)

    

Sur Linux :

- Utilisez votre gestionnaire de paquets yum install

````
sudo yum install git-flow ou sudo apt-get install git-flow
````
Initialisation :

- Pour commencer à utiliser GitFlow, vous devez d’abord initialiser votre dépôt avec GitFlow. Cela créera les branches principales et configurera certaines options :

````
git flow init
````

Branches de fonctionnalité :

- Créez une nouvelle branche de fonctionnalité à partir de la branche Develop :

````
git flow feature start <nom>
````
- Lorsque vous avez terminé, fusionnez la branche de fonctionnalité dans Develop :

````
git flow feature finish <nom>
````
Branches de release :

- Créez une nouvelle branche de release à partir de la branche Develop :

````
git flow release start <version>
````
- Lorsque vous avez terminé les tests et les corrections, fusionnez la branche de release dans Master et Develop, puis étiquetez-la avec la version :

````
git flow release finish <version>
````
Branches de hotfix :

- Créez une nouvelle branche de hotfix à partir de la branche Master :

````
git flow hotfix start <version>
````
- Lorsque vous avez corrigé le bug critique, fusionnez la branche de hotfix dans Master et Develop, puis étiquetez-la avec la version :

````
git flow hotfix finish <version>
````

En utilisant ces commandes, vous pourrez gérer efficacement votre flux de travail avec GitFlow. 🚀 
En suivant ces étapes, vous pourrez utiliser GitFlow efficacement pour gérer vos versions et collaborer en équipe. 🚀 