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

## Temporarily ignore file ##
    git update-index --assume-unchanged path/to/file

keep tracking again:

    git update-index --no-assume-unchanged path/to/file

### Aliases ###
    git config --global alias.co checkout
    git config --global alias.st status
    git config --global alias.br branch
    git config --global alias.qlog 'log --oneline --graph'
    git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
    git config --global alias.unstage 'reset HEAD --'

### Merging a trunk into a branch ###
    git merge --no-ff svn/trunk

### Show all branches with time of last commit ###
    # Credit http://stackoverflow.com/a/2514279
    for branch in `git branch | grep -v HEAD`;do echo -e `git show --format="%ci %cr" $branch | head -n 1` \\t$branch; done | sort -r
