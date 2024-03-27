# A quoi ça ressemble, en situation?

## Utiliser Git
___
### Le brief
___

Alex veut créer un site pour poster ses photos. Il décide d'utiliser Git et GitHub pour pouvoir reçevoir de l'aide de son ami Béa, qui va réaliser les élements interractifs du site.  

### Création du projet
___

Après avoir [installé](linkTBA) Git sur son terminal et fait sa configuration, Alex crée un dossier "site-photo", dans lequel il génère un _repository_ local Git grace à la commande:

```
git init
```

Dans GitHub, il crée un repo distant vide du même nom, et en récupère la clé SSH afin d'établir le lien entre son répo local (sur son ordinateur) et distant (sur GitHub).

\\ screenshot GitHub clé SSH

Pour faire ça, avec le dossier courant ouvert dans le Terminal, il inscrit la commande:

```
git remote add origin [cleSSH]
```

Il vérifie ensuite que la connection est bien établie avec:

```
git remote -v
```

Il crée un fichier README.md dans le _repository_ qu'il rédige pour communiquer les tenants de son projets. Avec la commande:
```
git status
``` 
il vérifie l'état de son _working directory_ et de la zone de _staging_. Il voit ainsi que son fichier README.md n'est npas tracké, et que ses changements ne sont pas mis dans la zone de _staging_. 
\\ sc untracked README.md 

Il règle ça avec la commande:
```
git add README.md
```
Le fichier est désormais dans le _staging_, Alex peut verifier ça en remandant un **git status**, ou **gst** pour aller plus vite.
\\sc gst now added

Pour valider les changements du nouveau fichier README.md, A utilise:
```
git commit -m "docs: created README.md and wrote its contents"
```
La commande inscrit ainsi dans l'historique du _repository_ git que Alex à crée et modifié le fichier README.md à la racine du _repository_ "site-photo".  

A souhaite maintenant porter ces changements, et l'état actuel de son _repo_ local vers son _repo_ distant GitHub. En utilisant:
```
git push origin main
```
il "pousse" l'état du projet vers le _repo_ distant défini comme _origin_, décrit par l'historique des modifications incrit par chaque commit (dans ce cas, un seul commit, contenant comme modifications la création d'un fichier et le changement de son contenu), sur la branche _main_.  
Sur GitHub, s'il actualise maintenant la page du _repo_ distant, il peut voir que le fichier README.md est bien présent.  
\\ sc github updaté

Alex continue de travailler ainsi sur son site. Une fois satisfait, il peut maintenant partager le repo à Béa facilement, en lui transmettant le lien du _repo_ GitHub.  


### Récupération du projet par un collaborateur
___

Après avoir reçu le lien du _repo_ distant GitHub, Béa fait un Fork du _repo_ et récupère clé SSH du Fork qu'elle à créé. 
\\ sc GitHub fork et clé SSH

Dans son Terminal sur son ordinateur, elle tape:
```
git clone [lienSSH]
```
Le _repo_ distant à ainsi été reprodruit dans le dossier courant ou elle se trouve. Le lien **origin** entre son nouveau _repo_ local et le _repo_ distant est automatiquement fait.  
Elle doit maintenant rattacher son local au _repo_ d'Alex, afin de pouvoir facilement récuperer les modifications qu'il **push**. Pour cela, elle utilise:
```
git remote add upstream [SSHAlex]
```
Elle est désormais prête à travailler.

### Travailler ensemble

Pour travailler sur le menu du site, Béa crée une **branche**.
```
git branch -c menu
git switch branch menu
```

Elle se trouve désormais dans la branche _menu_, sa branche _main_ restera inaffectée par tout changement qu'elle effectue sur la branche _menu_.  
Après avoir travaillé un moment, elle se rends compte qu'Alex à **push** des changements. Elle doit les recupérer.  
```
git fetch origin main
```

Elle vérifie s'il y a des conflits. N'ayant pas travaillé sur la branche _main_, il n'y en a pas. Elle peut donc **merge**.
```
git merge
```

Lorsque son travail sur le menu est terminé, elle doit maintenant **merge** la branche _menu_ sur sa _main_.  
Elle se deplace dans la branche _main_, celle sur laquelle elle veut porter les changements de sa branche.

```
git switch branch main
git merge menu
```

Le terminal l'informe d'un conflit dans un des fichiers, car elle et Alex y ont tout les deux apposé des changements.
// sc conflict

Le message l'informe d'où trouver le conflit. Béa n'a qu'a se rendre dans le fichier affecté et corriger le conflit, puis **commit** la correction.
```
git add [fichier]
git commit -m "feat: added Menu  

Fixed conflict with [file]"
```

Le menu est maintenant intégré à son _repo_. Elle teste le code, et tout fonctionne bien. Elle peut maintenant supprimer la branche _menu_
```
delete branch menu
```

Elle n'a plus qu'à **push** ses changements sur son _repo_ distant.
```
git push origin main
```

Si elle actualise le _repo_ GitHub, le site, détectant des changements entre son **fork** et le _repo_ d'Alex, il lui propose de faire un **pull request**, pour proposer à Alex de recupérer le menu qu'elle à créé et de l'ajouter à son _repo_.

\\sc pull request

Elle remplit le formulaire de Pull Request en renseignant le changement qu'elle à réalisé, puis l'envoie à Alex.  

Alex, lui, peut désormais voir le **pull request** de Béa, et vérifier les changements qu'elle à réalisé. C'est à lui de **review** le code de Béa, et de choisir s'il l'accepte et l'intègre au sien, s'il pose des **issues** pour qu'elle modifie des points de son code, ou s'il le refuse.  

Il peuvent de cette façon travailler sur différentes features en parrallèle, jusqu'à ce que leur site soit "terminé".

## Utiliser Git Flow
___
### Le brief

Satsifait avec le site photo d'Alex, le duo decide d'entamer un travail sur un autre site, cette fois pour faire une boutique en ligne pour le commerce de Béa. Cette dernière suggère d'utiliser Git-Flow pour ce projet, afin de fluidifier le processus de branches.  

### Création du projet
Cette fois, et avec Git-Flow [installé](linkTBA), après avoir fait son **git init**, Alex initialise en plus un _repo_ Git-Flow
```
git flow init
```
ce dernier crée des branches en plus de la main, notamment _develop_ sur laquelle il déplace automatiquement Alex pour en faire le _working directory_, mais configure en plus des préfixes de nomenclature pour les branches selon leur fonction: _feature_ pour des fonctionalités, _hotfix_ pour la réparation de bugs, _release_ pour le déployage de nouvelles versions en ligne.  

Après avoir **fork** et **clone** le projet, Béa devra cette fois aussi entrer la commande **git flow init**.

### Travailler ensemble

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


<REF-----------
[installé](linkTBA)
----------->
