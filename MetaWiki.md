I use gollum for hosting this wiki on GitHub.

## Workflow for allowing pull requests: (since GitHub doesn't allow pull requests for wikis.)

* `git clone /.../wiki.git
* `git remote add wiki.wiki https://github.com/Felix-Petersen/wiki.wiki.git`
* `git remote set-url origin --add https://github.com/Felix-Petersen/wiki.wiki.git`
* `git fetch wiki.wiki`
* `git merge --allow-unrelated-histories wiki.wiki/master`
* `git commit`

* `git pull`
* `git pull wiki.wiki HEAD`
* `git push`