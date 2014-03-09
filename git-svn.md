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
