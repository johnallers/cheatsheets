### SVN Clone ###
~~_Consider setting global core.autocrlf to false to avoid line ending issues._~~

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

### Import svn ignores ###

    git svn show-ignore >> .git/info/exclude

### Git SVN Fetch Skip revisions ###
This is useful if you need to skip a botched SVN revision. For instance, a deleted then recreated SVN branch might cause git-svn to re-fetch all the revisions again to find a matching parent commit. In this case you can skip the revision where the bad branch was created to avoid re-fetching all commits.

    git svn fetch -r BASE:665
    git svn fetch -r 667:HEAD
