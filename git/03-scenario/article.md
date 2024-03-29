<p align="center"><img width="600"src="../../images/git-logo.png"/><p>

# Git en situation

### Le brief

---

Alex veut créer un site pour poster ses photos. Il décide d'utiliser Git et GitHub pour pouvoir recevoir de l'aide de son ami Béa, qui va réaliser les élements interactifs du site.

### Création du projet

---

Après avoir [installé](/git/02-install/install.md) Git sur son terminal et fait sa configuration, Alex créer un dossier "site-photo", dans lequel il génère un _dépôt_ local Git grace à la commande:

```
git init
```

Dans GitHub, il crée un _dépôt_ distant vide du même nom, et en récupère la clé SSH afin d'établir le lien entre son _dépôt_ local (sur son ordinateur) et distant (sur GitHub).

![cleSSHAlex](/images/03-scenario/01SSH.jpg)

Pour faire ça, avec le dossier courant ouvert dans le Terminal, il inscrit la commande:

```
git remote add origin [cleSSH]
```

Il vérifie ensuite que la connection est bien établie avec:

```
git remote -v
```

![remoteCorrect](/images/03-scenario/02REMOTE.jpg)

Il crée un fichier README.md dans le _dépôt_ qu'il rédige pour communiquer les tenants de son projet. Avec la commande:

```
git status
```

Il vérifie l'état de son _index_ (zone de staging). Il voit ainsi que son fichier README.md n'est pas tracké, et que ses changements ne sont pas mis dans le _dépôt_.  
![untracked](/images/03-scenario/03UNTRACKED.jpg)

Il règle ça avec la commande:

```
git add README.md
```

Le fichier est désormais dans le _dépôt_, Alex peut verifier ça en demandant un **git status**,

![trckedfiles](/images/03-scenario/04TRACKED.jpg)

> [!TIP] > **gst** est un alias de **git status**, avec 7 caractères en moins à taper !

Pour valider les changements du nouveau fichier README.md, Alex utilise:

```
git commit -m "docs: created README.md and wrote its contents"
```

La commande inscrite ainsi dans l'historique de l'_index_ git dit que Alex a crée et modifié le fichier README.md à la racine de "site-photo".

Alex souhaite maintenant porter ces changements, et l'état actuel de son _dépôt_ local vers son _dépôt_ distant GitHub. Il utilise:

```
git push origin main
```

Il "pousse" l'état du projet vers le _dépôt_ distant défini comme _origin_, décrit par l'historique des modifications incrit par chaque commit (dans ce cas, un seul commit, contenant comme modifications la création d'un fichier et le changement de son contenu), sur la branche _main_.  
Sur GitHub, s'il actualise maintenant la page du _dépôt_ distant, il peut voir que le fichier README.md est bien présent.

![pushed](/images/03-scenario/05PUSH.jpg)

Alex continue de travailler ainsi sur son site. Une fois satisfait, il peut maintenant partager le _dépôt_ à Béa facilement, en lui transmettant le lien du _dépôt_ GitHub.

### Récupération du projet par un collaborateur

---

Après avoir reçu le lien du _dépôt_ distant GitHub, Béa fait un Fork du _dépôt_ et récupère la clé SSH du Fork qu'elle a créé.

![fork](/images/03-scenario/06BEAFORK.jpg)

Dans son Terminal sur son ordinateur, elle tape:

```
git clone [lienSSH]
```

Le _dépôt_ distant a ainsi été reprodruit dans le dossier courant où elle se trouve. Le lien **origin** entre son nouveau _dépôt_ local et le _dépôt_ distant est automatiquement fait.  
Elle doit maintenant rattacher son local au _dépôt_ d'Alex, afin de pouvoir facilement récuperer les modifications qu'il **push**. Pour cela, elle utilise:

```
git remote add upstream [SSHAlex]
```

Elle est désormais prête à travailler.

### Travailler ensemble

---

Pour travailler sur le menu du site, Béa crée une **branche**.

```
git branch -c menu
git switch branch menu
```

Elle se trouve désormais dans la branche _menu_, sa branche main restera inaffectée par tout changement qu'elle effectue sur la branche menu.  
Après avoir travaillé un moment, elle se rends compte qu'Alex a **push** des changements. Elle doit les recupérer.

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

Le message l'informe où trouver le conflit. Béa n'a qu'à se rendre dans le fichier affecté et corriger le conflit, puis **commit** la correction.

```
git add [fichier]
git commit -m "feat: added Menu

Fixed conflict with [file]"
```

Le menu est maintenant intégré à son _dépôt_. Elle teste le code, et tout fonctionne bien. Elle peut maintenant supprimer la branche _menu_

```
delete branch menu
```

Elle n'a plus qu'à **push** ses changements sur son _dépôt_ distant.

```
git push origin main
```

Si elle actualise le _dépôt_ GitHub, le site, détectant des changements entre son **fork** et le _dépôt_ d'Alex, il lui propose de faire un **pull request**, pour proposer à Alex de recupérer le menu qu'elle à créé et de l'ajouter à son _dépôt_. Elle clique sur le bouton **Contribute** pour envoyer ses changements.

![Contribute](/images/03-scenario/07CONTRIBUTE.jpg)
![SendPR](/images/03-scenario/07CONTRIBUTE2.jpg)

Elle remplit le formulaire de _Pull Request_ en renseignant le changement qu'elle a réalisé et en vérifiant qu'aucun conflit n'est détécté, puis l'envoie à Alex.

Alex, lui, peut désormais voir le **pull request** de Béa, et vérifier les changements qu'elle a réalisé. C'est à lui de **review** le code de Béa, et de choisir s'il l'accepte et l'intègre au sien, s'il pose des **issues** pour qu'elle modifie des points de son code, ou s'il le refuse.

Il peuvent de cette façon travailler sur différentes features en parrallèle, jusqu'à ce que leur site soit "terminé".
