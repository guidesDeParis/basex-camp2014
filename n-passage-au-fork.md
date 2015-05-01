## mettre à jour ses sources 

```bash
git fetch
```

## Intégrer les modifications que l'on veut ajouter au dépôt SynopsX


## Forker le répertoire SynopsX depuis la page GitHub de AHN

https://github.com/ahn-ens-lyon/synopsx/fork


## Cloner le fork de SynopsX sur sa machine

Se placer à l'endroit où l'on veut forker le répertoire git 

```bash
git clone git@github.com:monCompteGitHub/synopsx.git # adresse à modifier
```

## Ajouter le remote upstream 

Lister les branches distantes

```bash
  git remote -v
```
Normalement vous ne disposez pour commencer que de deux remotes (par défaut origin) qui pointent vers votre fork :

origin  git@github.com:guidesDeParis/synopsx.git (fetch)
origin  git@github.com:guidesDeParis/synopsx.git (push)

Il vous faut encore ajouter un remote (upstream) pour lier ce fork aux sources sur AHN:

```bash
git remote add upstream git@github.com:ahn-ens-lyon/synopsx.git
```

Lister à nouveau les remotes, vous devez maintenant en avoir quatre, deux qui pointent vers votre fork, et deux vers les sources pour mettre à jour votre fork :

```bash
git remote -v
```

origin  git@github.com:guidesDeParis/synopsx.git (fetch)
origin  git@github.com:guidesDeParis/synopsx.git (push)
upstream  git@github.com:ahn-ens-lyon/synopsx.git (fetch)
upstream  git@github.com:ahn-ens-lyon/synopsx.git (push)

Mettre à jour ses sources upstream pour récupérer les dernières modifications

```bash
git fetch upstream
```

Si vous listez maintenant les branches, vous devriez voir apparaître les nouvelles branches de upstream :

```bash
git branch -a
```

nuelchateau ~/Sites/synopsx (master) git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/upstream/constantia
  remotes/upstream/dev
  remotes/upstream/donnerstag
  remotes/upstream/graal
  remotes/upstream/master
  remotes/upstream/templating
  remotes/upstream/vendredi

Il est désormais possible de travailler comme précédemment, mais vos modifications ne prendront effet que sur votre copie locale et vous pousserez sur votre fork. Les modifications à intégrer sur une branche de AHN doivent se faire au moyen d'un push resquest depuis l'interface de GitHub, ce qui nous permettra de gérer les modifications.

On travaillera par exemple sur une nouvelle fonctionnalité sur une nouvelle branche qui sera dérivée de la branche upstream vendredi :

```bash
git co vendredi
```

Avec la dernière version de git la branche vendredi est clonnée depuis le remote upstream


Par exemple
