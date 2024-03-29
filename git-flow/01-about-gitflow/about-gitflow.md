<p align="center"><img width="600"src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*SK4JGjtWs9BsfGGXOrnnig.png"/><p>

# À propos de Git-Flow

Git-Flow est une extention développée par Vincent Driessen en 2010.  
Elle permet de gérer le _versionning_ de projets en collaboration, et de fluidifier le _workflow_.  

Git-flow definit des préfixes de branches appliqués automatiquement lors de la création de branches, et ces préfixes sont utilisés par l'extention pour définir les directions des _merges_.

Concrètement, elle utilise une branche **main** réservée aux versions "terminées" de l'application, une branche de travail **develop**, des branches **features** et **hotfix** pour travailler sur les fonctionalités et bugs en isolation, et des branches **release** pour préparer les nouvelles versions avant déployement.  

Les **features** push vers la **develop**, la **develop** vers la branche **release** qui à son tour push sur la branche **main**, et les **hotfix** push sur la **main** et **develop** en "même temps".

![schemaDirectionsPush](/images/git-flow-4.png)
