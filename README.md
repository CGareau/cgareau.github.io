# Wiki 4D

`Wiki 4D` regroupe différents articles et process techniques. Vous pouvez contribuer au développement du site ou à l'ajout de contenu technique

## Contribuer

Intéressé(e) pour contribuer au wiki ? Wiki 4D est un projet open source, fruit de la collaboration de passionés de la technologie 4D.

### Prévisualiser le site web en local

Si vous souhaitez prévisualiser le site localement (par exemple pour proposer une modification ou un ajout) :

* Clone le repository en local (`git clone https://github.com/CGareau/cgareau.github.io.git`)

* `cd` dans le dossier `cgareau.github.io`

* Installer Jekyll en suivant les instructions liées à votre plateforme sur le [site de Jekyllrb](https://jekyllrb.com/docs/installation/)

* Run `bundle exec jekyll serve` pour démarrer la prévisualisation du site en local

* Se rendre à l'adresse [localhost:4000](http://127.0.0.1:4000/) dans votre navigateur.

### Modifier ou ajouter du contenu

* créer une nouvelle branche : `git checkout -b nom_de_votre_branche`

* effectuer votre modification ou votre ajout

* avoir la liste des modifications que vous avez faites : `git status`

* ajouter vos modifications dans l'index : `git add .`

* ajouter vos modifications dans votre repository local : git commit -m "votre_texte_expliquant_la_modif_réalisée"

### Proposer votre modification

* envoyer le contenu de vos modifications dans le repository distant : `git push origin nom_de_votre_branche`

### Intégrer votre modification dans la branche principale

**_Une fois que vos modifications ont été validées_**

* mettre les modifs dans la branche master : `git rebase master`

* se mettre dans la branche master : `git checkout master`

* merger vos modifications : `git merge nom_de_votre_branche`

* supprimer votre branche : `git branch -d nom_de_votre_branche`

* récupérer les dernières mises à jour à partir du repository distant : `git fetch`

* récupérer les dernières mises à jour et les merger avec votre travail : `git pull origin master`

* ajouter vos modifications dans le repository distant : `git push origin master`