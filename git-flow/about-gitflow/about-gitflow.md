# About Git-Flow

Git-Flow est un modèle de _branching_ alternatif rattaché à Git, cad qu'il offre des commandes alternatives à celle de Git pour créer, modifier, et merge des branches, permettant un workflow different.

## Differences avec le Workflow Git

    - Nomenclature automatique et catégorisée des branches par type
        - feature
        - hotfix
        - release
    - Organisation d'une branche de travail 'develop' vs branche 'main' vouée uniquement aux releases.
    - Merge des branches de hotfix sur la branche main ET develop en une commande.
    - Partage des branches fluidifé avec la commande de publish de branche feature

Git-Flow est optimisé pour un dévelopement sur modèle de "release", où des changements multiples sont déployés par packs périodiques sur l'application.