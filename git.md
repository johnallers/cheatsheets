### Set origin and make initial push ###
    git remote add origin <url>
    git push -u origin master

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

### Show differences between files in different branches ###
    git difftool somebranch:UNREADME otherbranch:README

### Aliases ###
    git config --global alias.co checkout
    git config --global alias.st status
    git config --global alias.br branch
    git config --global alias.qlog 'log --oneline --graph'
    git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

### SVN Clone ###
    git svn clone -s --prefix=svn/ -r --no-minimize-url HEAD https://repo

### Apply SVN patch (Git Bash) ###
    cd /path/to/patch
    patch -p0 < /path/of/patch.patch
