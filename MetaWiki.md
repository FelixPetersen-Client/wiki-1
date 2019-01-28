I use gollum for hosting this wiki on GitHub.

## Workflow for allowing pull requests: (since GitHub doesn't allow pull requests for wikis.)

### Setup
```sh
git clone .../wiki.git
git remote add wiki.wiki .../wiki.wiki.git
git remote set-url origin --add .../wiki.wiki.git
git fetch wiki.wiki
git merge --allow-unrelated-histories wiki.wiki/master
git commit
```

### Synchronize
* `git pull`
* `git pull wiki.wiki HEAD`
* resolve conflicts
* `git commit`
* `git push`

If no conflict:
```
git pull
git pull wiki.wiki HEAD
git push
```