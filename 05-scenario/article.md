# A quoi ça ressemble, en situation?

## Git-ing
___
### cas
___

Alex veut créer un site pour poster ses photos. Il décide d'utiliser Git et GitHub pour pouvoir reçevoir de l'aide de son ami Béa.  

### creation
___

Après avoir [installé] Git sur son terminal et fait sa configuration, Alex crée un dossier "site-(thême)", dans lequel il génère un _repository_ local Git grace à la commande:

```
git init
```

Dans GitHub, il crée un repo distant vide du même nom, et en récupère la clé SSH afin d'établir le lien entre son répo local (sur son ordinateur) et distant (sur GitHub).

\\\ screenshot GitHub clé SSH

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
il vérifie l'état de son _working directory_ et de la zone de _staging_. Il voit ainsi que son fichier README.md n'est ni tracké, et que ses changements ne sont pas mis dans la zone de _staging_. 
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
La commande inscrit ainsi dans l'historique du _repository_ git que Alex à crée et modifié le fichier README.md à la racine du _repository_ "site-(thême)".  

A souhaite maintenant porter ces changements, et l'état actuel de son _repo_ local vers son _repo_ distant GitHub. En utilisant:
```
git push origin main
```
il "pousse" l'état du projet vers le _repo_ distant défini comme _origin_, décrit par l'historique des modifications incrit par chaque commit (dans ce cas, un seul commit, contenant comme modifications la création d'un fichier et le changement de son contenu).  
Sur GitHub, s'il actualise maintenant la page du _repo_ distant, il peut voir que le fichier README.md est bien présent.  

Alex continue de travailler ainsi sur son site. Une fois satisfait, il peut maintenant partager le repo à Béa facilement, en lui transmettant le lien du _repo_ GitHub.  


### recupération
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

### Working

She decides to make a branch to work on the menu.
git branch menu
git switch branch menu

She's now in a branch, all changes that she makes here won't appear on the main branch, or any other branch that she makes. She can work peacefully on the menu. 
Once she's done, she realises Alex made some changes to the project.

Béa needs to retrieve the changes.
git fetch
check for conflict, there are none with the main branch.
git merge

She now has to merge the menu branch with the main branch to add the feature she worked on to the project.
git merge (branches)

With Alex's change, one file now triggers a conflict when trying to merge her branch
//sc conflict

The conflict message tells her where the conflict is found, so she can go and fix the conflict however she sees fit. Once that is done, she just needs to run a regular **commit** of the now fixed conflicted file.
git add
git commit

The feature is now integrated into her local _repo_'s main branch. She tests it out, and all is working well. She can delete the branch that now served its purpose.
delete branch

All she has to do now is push her changes to her own remote github _repo_
git push origin main

Now on github, since that repo is forked, it'll detect that she made changes, and offer she makes a PULL REQUEST. That will allow her to show her work to Alex, and ask him to retrieve them and apply them to his main branch.

\\sc pull request

She properly fills out the PR with details of her work, and sends out the request.

Alex now can see her pull request, and can review the changes she made. It's up to him now to accept the changes and integrate them to his repo, or emmit an issue with them for her to fix. In the meantime, Béa can work on other features, and so can Alex.

## With Git-Flow

Alex and Béa are content with their website, they now want to make another one for Béa's business. This time, Béa suggests they use Git-Flow.

Once more, Alex creates both local and remote repos, but this time, after his **git init**, he also uses
```
git flow init
```
which creates branches beyond the main. A develop, which will be used to push changes to their own remote repos, and tags for future branches to classify them between features, hotfixes, and release branches. 


<REF---------------------->
[installé]