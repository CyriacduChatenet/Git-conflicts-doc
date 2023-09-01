# Gestion des conflits Git

## 💻  Workflow local
### Lors de la création d'une nouvelle feature / enhancement / fix :
- git checkout develop
- git pull origin develop
- git checkout -b (feature/branch_name ou enhancement/branch_name ou fix/branch_name)
Si il existe un outil de tickets associé au projet (AirTable, Trello, Asana, etc.), préfixer le nom de la branche par l'identifiant du ticket : fix/186-user-jwt-security
### Rebase à faire car conflit sur la PR :
- git checkout develop
- git pull origin develop
- git checkout nom_de_ma_branche
- git rebase develop

- git checkout -b nom_de_ma_branch-b
- git push origin nom_de_ma_branch-b
⚠️  Le suffixe du nom de la branche est un "incrément" de l'alphabet, par ex. :
feature/user-auth (branche initiale)
feature/user-auth-b (premier rebase)
feature/user-auth-c (deuxième rebase)
...
- ➡️  Refaire une PR avec mes changements
### Résolution des conflits :
- Prendre le ou les bon(s) bout de code
- git add .
- git rebase --continue
Et réitéré jusqu'à ce qu'il n'y ait plus de conflit

## 🐙  Workflow depuis Github
### Gestion des branches
- Une branche = une pull request (PR)
Si il n'y a pas de CI, la validation doit être faite par :
le lead du projet
les devs qui travaillent sur la même feature / épic
⚠️  Les branches feature / enhancement / fix sont toujours squash & merge vers la branche de dev (théoriquement develop)
- Supprimer la branche après le merge
- Utilisation et signification des labels
### Type de PR
- WIP = label par défaut, code instable en cours de développement
- Feature = identification du type de PR
- Enhancement = identification du type de PR
- Bug = identification du type de PR
- Validation des PR
- Need Review = PR terminée, prête à être review par l'équipe
- GTG = PR validée, prête à être merge
- Request Changes = PR non validée avec demandes de modifications
Autres
- Blocker = PR devant être traité en priorité
- Documentation = ajout de documentation dans la PR
- Question = Question pouvant bloquer la validation de la PR
- Rebased = PR faisant référence à son itération précédente après un rebase
- Standby = PR en attente d'éléments ou bloquer pour diverses raisons