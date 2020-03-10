# Wiki 4D

_`Wiki 4D` regroupe différents articles et process techniques. Vous pouvez contribuer au développement du site ou à l'ajout de contenu technique._


## Contribuer

Intéressé(e) pour contribuer ? Vous êtes le bienvenu !
`Wiki 4D` est un projet open source, fruit de la collaboration de passionés de la technologie 4D.


### Prévisualiser le site web en local

Si vous souhaitez prévisualiser le site localement (par exemple pour proposer une modification ou un ajout) :

* Cloner le repository en local (`git clone https://github.com/CGareau/cgareau.github.io.git`)

* Exécuter `cd` dans le dossier `cgareau.github.io`

* Installer Jekyll en suivant les instructions liées à votre plateforme sur le [site de Jekyllrb](https://jekyllrb.com/docs/installation/)

* Exécuter `bundle exec jekyll serve` pour démarrer la prévisualisation du site en local

* Se rendre à l'adresse [localhost:4000](http://127.0.0.1:4000/) dans votre navigateur.


### Modifier ou ajouter du contenu en local

* Créer une nouvelle branche `git checkout -b nom_de_votre_branche`

* Effectuer votre modification ou votre ajout en local

* Obtenir la liste des modifications que vous avez effectuées `git status`

* Ajouter toutes vos modifications dans votre index en local `git add .`

* Ajouter vos modifications dans votre repository local `git commit -m "votre_texte_expliquant_la_modif_réalisée"`


### Proposer votre modification sur GitHub

* Envoyer le contenu de vos modifications dans le repository distant `git push origin nom_de_votre_branche`

* Soumettre une `pull request` en expliquant le travail effectué


### Intégrer votre modification dans GitHub

**_Une fois que votre `pull request` a été validée_**

* Rejouer vos modifications dans la branche master `git rebase master`

* Se mettre dans la branche master `git checkout master`

* Intégrer vos modifications dans votre repository local `git merge nom_de_votre_branche`

* Supprimer votre branche : `git branch -d nom_de_votre_branche`

* Récupérer les dernières mises à jour des autres contributeurs à partir du repository distant `git fetch`

* Intégrer ces mises à jour dans votre repository local `git pull origin master`

* Intégrer vos modifications dans le repository distant `git push origin master`