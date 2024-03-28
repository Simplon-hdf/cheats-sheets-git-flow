## ![Logo gitflow](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*SK4JGjtWs9BsfGGXOrnnig.png)

---

# Introduction

- GitFlow est un modèle de gestion des branches Git qui facilite l’organisation du cycle de développement d’un projet. Voici comment l’installer et l’utiliser :

# Installation

- Pour installer GitFlow, vous devez d’abord vous assurer que Git est déjà installé sur votre système.

- Ensuite, installez le plugin GitFlow. Voici quelques options :

Sur macOS :

- Utilisez Homebrew :

```
brew install git-flow-avh
```

Ou avec Macports :

```
port install git-flow-avh
```

Sur Windows :

- Utilisez [GitFlow pour Windows](https://github.com/nvie/gitflow/wiki/Windows)

- Utilisez GitFlow pour [Windows avec Git Bash](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/Gitflow-Windows-Install-Git-Flow-Installation)

Sur Linux :

- Utilisez votre gestionnaire de paquets yum install

```
sudo yum install git-flow ou sudo apt-get install git-flow
```

Initialisation :

- Pour commencer à utiliser GitFlow, vous devez d’abord initialiser votre dépôt avec GitFlow. Cela créera les branches principales et configurera certaines options :

```
git flow init
```

Branches de fonctionnalité :

- Créez une nouvelle branche de fonctionnalité à partir de la branche Develop :

```
git flow feature start <nom>
```

- Lorsque vous avez terminé, fusionnez la branche de fonctionnalité dans Develop :

```
git flow feature finish <nom>
```

Branches de release :

- Créez une nouvelle branche de release à partir de la branche Develop :

```
git flow release start <version>
```

- Lorsque vous avez terminé les tests et les corrections, fusionnez la branche de release dans Master et Develop, puis étiquetez-la avec la version :

```
git flow release finish <version>
```

Branches de hotfix :

- Créez une nouvelle branche de hotfix à partir de la branche Master :

```
git flow hotfix start <version>
```

- Lorsque vous avez corrigé le bug critique, fusionnez la branche de hotfix dans Master et Develop, puis étiquetez-la avec la version :

```
git flow hotfix finish <version>
```

En utilisant ces commandes, vous pourrez gérer efficacement votre flux de travail avec GitFlow. 🚀
En suivant ces étapes, vous pourrez utiliser GitFlow efficacement pour gérer vos versions et collaborer en équipe. 🚀
