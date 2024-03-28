<p align="center"><img width="600"src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*SK4JGjtWs9BsfGGXOrnnig.png"/><p>

# Git-Flow

## Table des matières

<ul>
    <li><a href="./02-install/install.md">Installation</a></li>
    <li><a href="./01-about-gitflow/about-gitflow.md">À propos de Git flow</a></li>
    <li><a href="./03-scenario/scenario.md">Utiliser Git flow</a></li>
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
            <td align="right"><code>git flow init</code></td>
            <td>Initialise le dossier courant en depot Git-Flow local et change la branche courante vers develop</td>
        </tr>
        <tr>
            <th colspan="3" align="left">Branches</th>
        </tr>
        <tr>
            <td align="right"><code>git flow feature start [branche]</code></td>
            <td>Créer une branche de feature et en fait la branche courante</td>
        </tr>
        <tr>
            <td align="right"><code>git flow feature finish [branche]</code></td>
            <td>Merge la branche de feature sur la branche develop, et supprime la branche feature</td>
        </tr>
        <tr>
            <td align="right"><code>git flow hotfix start [branche]</code></td>
            <td>Créer une branche de déboggage et en fait branche courante</td>
        </tr>
        <tr>
            <td align="right"><code>git flow hotfix finish [branche]</code></td>
            <td>Merge la branche hotfix à la branche main et develop, et supprime la branche hotfix</td>
        </tr>
        <tr>
            <td align="right"><code>git flow release start [branche]</code></td>
            <td>Créer une nouvelle branche de release a partir de la branche develop</td>
            <tr>
                <td align="right"><code>git flow release finish [branche]</code></td>
                <td>Merge la branche release sur la branche main et supprime la branche release </td>
            </tr>
        </tr>
            <th colspan="3" align="left">Partage de branche</th>
        </tr>
        <tr>
            <td align="right"><code>git flow feature publish [branche]</code></td>
            <td>Push la branche feature sur le repo distant</td>
        </tr>
        <tr>
            <td align="right"><code>git flow feature pull [remote] [branche]</code></td>
            <td>Recupère une branche du repo distant</td>
        </tr>
    </tbody>

</table>
