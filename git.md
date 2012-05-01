### View all branches ###
    git branch -a

### Discard all unstaged changes ###
    git checkout -- .

### Fix last commit message ###
    git commit --amend

### Rebase all commits from master onto the current branch ###
    git rebase master

### Stash untracked files ###
    git stash -u

### Aliases ###
    git config --global alias.co checkout
    git config --global alias.st status
    git config --global alias.br branch
    git config --global alias.qlog 'log --oneline --graph'

### SVN Clone ###
    git svn clone -s --prefix=svn/ -r --no-minimize-url HEAD https://repo
