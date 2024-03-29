<p align="center"><img width="600"src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*SK4JGjtWs9BsfGGXOrnnig.png"/><p>

# Git-Flow

---

Git-Flow est un modèle de _branching_ alternatif rattaché à Git, c'est à dire qu'il offre des commandes alternatives à celle de Git pour créer, modifier, et merge des branches, permettant un workflow différent.

## Table des matières

[Workflow Git Flow](#differences-avec-le-workflow-git)  
[Cheat Sheet](#cheat-sheet)

## Sommaire

<ul>  
    <li><a href="./02-install">Installation</a></li>  
    <li><a href="./01-about-gitflow">À propos de Git flow</a></li>
    <li><a href="./03-scenario">Utiliser Git flow</a></li>
</ul>

## Differences avec le Workflow Git

---

Git-Flow est optimisé pour un dévelopement sur modèle de "release", où des changements multiples sont déployés par packs périodiques sur l'application.

Git-Flow crée automatiquement une branche **develop** qui sert de branche de travail. La branche **main** reste ainsi stable pour l'utilisateur malgré les changements sur lesquels les devs travaillent.

![main&dev](/images/git-flow-1.png)

À partir de cette branche **develop**, les devs peuvent créer en local des branches de **feature** pour travailler sur chaque nouvelle fonctionnalité en parrallèle. Chaque **feature** terminée et validée est ensuite merge sur la branche **develop**.

![feature](/images/git-flow-2.png)

Pour pouvoir modifier la branche **main** auquel l'utilisateur a accès, les devs passent par une branche **release** qui communique les changements de la branche **develop**, et les merge à la **main**.

![release](/images/git-flow-3.png)

Lors d'une détection de bugs, les branches **hotfix**, naissant de la branche **main** permettent de les résoudre, et ces changements s'appliquent simultanément aux la branche **main** et **develop**. Ainsi, l'apparition de bugs n'interromp pas le travail des differents collaborateurs.

![hotfix](/images/git-flow-4.png)

## Cheat Sheet

---

<table>
    <thead>
        <tr>
            <th>Commande</th>
            <th>Fonction</th>
            <th>Exemple</th>
        </tr>   
    </thead>
    <tbody>
        <tr>
            <th colspan="3" align="left">Setup & Init</th>
        </tr>
        <tr>
            <td align="right"><code>git flow init</code></td>
            <td>Initialise un dossier .git vide, dans le dépôt courant et déplace l'utilisateur sur la branche develop</td>
            <td></td>
        </tr>
        <tr>
            <th colspan="3" align="left">Branches</th>
        </tr>
        <tr>
            <td align="right"><code>git flow feature start [branche]</code></td>
            <td>Crée une branche de feature et en fait la branche courante</td>
            <td align="right"><code>git flow feature start header</code></td>
        </tr>
        <tr>
            <td align="right"><code>git flow feature finish [branche]</code></td>
            <td>Fusionne la branche de feature sur la branche develop, et supprime la branche feature</td>
            <td align="right"><code>git flow feature finish header</code></td>
        </tr>
        <tr>
            <td align="right"><code>git flow hotfix start [branche]</code></td>
            <td>Crée une branche de déboggage et en fait la branche courante</td>
            <td align="right"><code>git flow hotfix start fix-api-url</code></td>
        </tr>
        <tr>
            <td align="right"><code>git flow hotfix finish [branche]</code></td>
            <td>Fusionne la branche hotfix à la branche main et develop, et supprime la branche hotfix</td>
            <td align="right"><code>git flow hotfix finish fix-api-url</code></url>
        </tr>
        <tr>
            <td align="right"><code>git flow release start [numero de version]</code></td>
            <td>Crée une nouvelle branche de release à partir de la branche develop</td>
            <td>git flow release start 1.0.0</td>
            <tr>
                <td align="right"><code>git flow release finish [numero de version]</code></td>
                <td>Fusionne la branche release sur la branche main et supprime la branche release </td>
                <td align="right"><code>git flow release finish 1.0.0</code></td>
            </tr>
        </tr>
            <th colspan="3" align="left">Partage de branche</th>
        </tr>
        <tr>
            <td align="right"><code>git flow feature publish [branche]</code></td>
            <td>Pousse la branche feature sur le dépôt distant</td>
            <td align="right"><code>git flow feature publish header</code></td>
        </tr>
        <tr>
            <td align="right"><code>git flow feature pull [remote] [branche]</code></td>
            <td>Récupère une branche d'un dépôt distant</td>
            <td align="right"><code>git flow feature pull origin menu</code></td>
        </tr>
    </tbody>

</table>
