<p align="center"><img width="600"src="./images/git-logo.png"/><p>

# Git

Git est un système de contrôle de version qui trace les changements dans le code source.

- Il utilise des dépôts pour stocker des instantanés complets du projet à chaque commit.

- Les branches permettent de travailler sur des versions distinctes du code. Les commits enregistrent les modifications avec des messages descriptifs.

- Git conserve un historique complet des changements pour suivre l'évolution du projet.

## Table des matières

<ul>
    <li><a href="./git/02-install/install.md">Installation</a></li>
    <li><a href="./git/03-scenario/article.md">Utiliser Git</a></li>
    <li><a href="./git/01-about-git/about-git.md">More about Git</a></li>
    <li><a href="./git-flow/README.md">Git-Flow</a></li>
</ul>

## Cheat sheet

<table>
    <thead>
        <tr>
            <th>Commande</th>
            <th>Fonction</th>
        </tr>   
    </thead>
    <tbody>
        <tr>
            <th colspan="3" align="left">Setup & Init</th>
        </tr>
        <tr>
            <td align="right"><code>git init</code></td>
            <td>Initialise le dossier courant en depot Git local</td>
        </tr>
         <tr>
            <td align="right"><code>git clone [url]</code></td>
            <td>Récupère l'entièreté d'un dépot distant via URL</td>
        </tr>
        <tr>
        <tr>
            <th colspan="3" align="left">Staging</th>
        </tr>
            <td align="right"><code>git status</code></td>
            <td>Affiche les fichiers modifiés dans le working directory</td>
        </tr>
        <tr>
            <td align="right"><code>git add [fichier]</code></td>
            <td>Ajoute un fichier au prochain commit (en staging)</td>
        </tr>
        <tr>
            <td align="right"><code>git reset [fichier]</code></td>
            <td>Enlève un fichier du staging tout en gardant les changement dans le working directory</td>
        </tr>
         <tr>
            <td align="right"><code>git diff</code></td>
            <td>Différence des changements pas en staging</td>
        </tr>
        <tr>
            <td align="right"><code>git diff --staged</code></td>
            <td>Différence du staging mais pas encore commit</td>
        </tr>
        <tr>
            <td align="right"><code>git diff [branche locale] [branche distante]</code></td>
            <td>Compare les différences entre une brancge locale et distante</td>
        </tr>
        <tr>
            <td align="right"><code>git commit -m [message]</code></td>
            <td>Effectue le commit contenant les fichiers en staging</td>
        </tr>
        <tr>
            <th colspan="3" align="left">Branches</th>
        </tr>
        <tr>
            <td align="right"><code>git branch -av</code></td>
            <td>Liste vos branches. Un * apparaitra à coté de la branche actuelle</td>
        </tr>
        <tr>
            <td align="right"><code>git branch [branche]</code></td>
            <td>Créer une nouvelle branche</td>
        </tr>
        <tr>
            <td align="right"><code>git switch [branche]</code></td>
            <td>Change la branche courante</td>
        </tr>
        <tr>
            <td align="right"><code>git branch -d [branche]</code></td>
            <td>Supprime la branche local</td>
        </tr>
        <tr>
            <td align="right"><code>git checkout --track</code></td>
            <td>Créer une nouvelle branche trackée à partir d'une branche distante</td>
            <tr>
                <td align="right"><code>git tag [tag-name]</code></td>
                <td>Créer un tag </td>
            </tr>
        </tr>
        <tr>
            <th colspan="3" align="left">Historique</th> 
        </tr>
        <tr>
            <td align="right"><code>git log</code></td>
            <td>Affiche l'historique commits</td>
        </tr>
        <tr>
            <td align="right"><code>git log -p [fichier]</code></td>
            <td>Affiche l'historique des commits sur un fichier spécifique</td>
        </tr>
        <tr>
            <td align="right"><code>git blame [fichier]</code></td>
            <td>Affiche l'historique des modifications, y compris l'auteur sur un fichier spécifique</td>
        </tr>
        <tr>
            <th colspan="3" align="left">Mise à jour et publication</th>
        </tr>
        <tr>
            <td align="right"><code>git remote -v</code></td>
            <td>Liste les remote configurés</td>
        </tr>
        <tr>
            <td align="right"><code>git remote show [remote]</code></td>
            <td>Affiche les informations de la remote</td>
        </tr>
        <tr>
            <td align="right"><code>git remote add [remote] [url]</code></td>
            <td>Ajoute une nouvelle remote au nom donné</td>
        </tr>
        <tr>
            <td align="right"><code>git fetch [remote]</code></td>
            <td>Récupère toutes les modifications de la remote sans merge les changements</td>
        </tr>
        <tr>
            <td align="right"><code>git pull [remote] [branche]</code></td>
            <td>Récupère les modifications de la branche, et les merge</td>
        </tr>
        <tr>
            <td align="right"><code>git push [remote] [branche]</code></td>
            <td>Poussant ses modifications sur la branche au repo distant</td>
        </tr>
        <tr>
            <th colspan="3" align="left">Merge & Rebase</th>
        </tr>
        <tr>
            <td align="right"><code>git merge [branche]</code></td>
            <td>Merge la branche dans la branche actuelle</td>
        </tr>
        <tr>
            <td align="right"><code>git rebase [branche]</code></td>
            <td>Réécrit l'historique des commit de la branche actuelle vers la branche spécifiée</td>
        </tr>
        <tr>
            <td align="right"><code>git rebase --abort</code></td>
            <td>Annule le processus de rebase en cours</td>
        </tr>
        <tr>
            <td align="right"><code>git rebase --continue</code></td>
            <td>Poursuit le processus de rebase après la résolution des conflits</td>
        </tr>
        <tr>
            <td align="right"><code>git mergetool</code></td>
            <td>Ouvre un outil de merge pour résoudre les conflits</td>
        </tr>
        <tr>
            <th colspan="3" align="left"    >Rétablir/Annuler</th>
        </tr>
        <tr>
            <td align="right"><code>git reset --hard</code></td>
            <td>Réinitialise le staging et le working directory à HEAD</td>
        </tr>
        <tr>
            <td align="right"><code>git checkout HEAD [fichier]</code></td>
            <td>Restaure un fichier a son état HEAD</td>
        </tr>
        <tr>
            <td align="right"><code>git revert [commit]</code></td>
            <td>Annule les modifications d'un commit spécifique</td>
        </tr>
        <tr>
            <td align="right"><code>git reset --hard [commit]</code></td>
            <td>Réinitialise le staging et le working directory au commit spécifié</td>
        </tr>
        <tr>
            <td align="right"><code>git reset [commit]</code></td>
            <td>Déplace la branche actuelle vers le commit spécifié</td>
        </tr>
        <tr>
            <td align="right"><code>git reset --keep [commit]</code></td>
            <td>Déplace la branche tout en conservant les modifications pas en staging</td>
        </tr>
    </tbody>

</table>
