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

#### If no conflict:
```sh
git pull
git pull wiki.wiki HEAD
git push
```
Or with \_Sidebar update:
```sh
git pull
git pull wiki.wiki HEAD
sed "/Copy of \_Sidebar\. Do \*\*not\*\* change/q" Home.md > _tmp_Home.md
sed -E "1d" _Sidebar.md >> _tmp_Home.md
mv _tmp_Home.md Home.md
git add Home.md
git commit -m "🤖 Auto-update Home.md"
git push
```

#### Aliases
* `git config alias.syncwiki '!git pull && git pull wiki.wiki HEAD && git push'`
* `git config alias.syncwiki '!git pull && git pull wiki.wiki HEAD && sed "/Copy of \_Sidebar\. Do \*\*not\*\* change/q" Home.md > _tmp_Home.md && sed -E "1d" _Sidebar.md >> _tmp_Home.md && mv _tmp_Home.md Home.md && git add Home.md && { git commit -m "🤖 Auto-update Home.md" ; git push; }'`

**`git syncwiki`**

`.zshrc`: `alias syncwiki="cd ~/Documents/wiki/wiki && git syncwiki"`
