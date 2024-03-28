# Git-flow en situation

### Le brief
___

Satsifait avec le [site photo d'Alex](/git/05-scenario/article.md), le duo decide d'entamer un travail sur un autre site, cette fois pour faire une boutique en ligne pour le commerce de Béa. Cette dernière suggère d'utiliser Git-Flow pour ce projet, afin de fluidifier le processus de branches.  

### Création du projet
___
Cette fois, et avec Git-Flow [installé](/git-flow/install/install.md), après avoir fait son **git init**, Alex initialise en plus un _repo_ Git-Flow
```
git flow init
```
ce dernier crée des branches en plus de la main, notamment _develop_ sur laquelle il déplace automatiquement Alex pour en faire le _working directory_, mais configure en plus des préfixes de nomenclature pour les branches selon leur fonction: _feature_ pour des fonctionalités, _hotfix_ pour la réparation de bugs, _release_ pour le déployage de nouvelles versions en ligne.  

Après avoir **fork** et **clone** le projet, Béa devra cette fois aussi entrer la commande **git flow init**.


### Travailler ensemble
___

Avec cet outil, au lieu de crée une branche via la commande Git, Alex et Béa utiliseront la commande Git Flow, par exemple pour créer le _header_ du site:
```
git flow feature start header
```

Git-flow crée alors automatiquement une branche **feature/header** sur laquelle elle déplace l'utilisateur.  
Une fois le travail de la branche terminé, entrer
```
git flow feature finish header
```
merge la branche sur le **develop**, et supprime la branche de feature.  

En faisant le **merge** du header, Alex à créé un bug, pour le résoudre il crée une branche de **hotfix**
```
git flow hotfix start bug_header
```

Il pourra regler le bug, et merge la branche de la même façon qu'une branche de feature.  

Pendant son travail sur la page de transaction, Béa rencontre un problème pour lequel elle à besoin de l'aide d'Alex. Elle peut simplement partager sa branch feature/transaction avec

```
git flow feature publish transaction
```

La branche est désormais disponible pour Alex sur le _repo_ distant, il peut la récuperer en local via:
```
git flow feature pull origin transaction
```

De cette façon, ils peuvent se transmettre le travail en cours d'une feature sans necessairement la **merge** sur leur _develop_.


<!----------- REF
[installé](https://github.com/Simplon-hdf/cheats-sheets-git-flow/blob/develop/01-install/Install.md)
----------->
