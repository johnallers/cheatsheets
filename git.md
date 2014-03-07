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
    git svn clone -s --prefix=svn/ -r HEAD --no-minimize-url https://repo

### Apply SVN patch (Git Bash) ###
    cd /path/to/patch
    patch -p0 < /path/of/patch.patch
    
### Configure git-svn to populate svn:mergeinfo ###

    git config --global svn.pushmergeinfo true  
    
### Merging a trunk into a branch ###
    git merge --no-ff svn/trunk

### Adding SVN branches to pull (.git/config) ###

    [svn-remote "svn"]
        url = http://example.com/path/to/project-x
        fetch = trunk:refs/remotes/git-svn
        fetch = branches/branch1:refs/remotes/branch1
