# Usefull git commands #

Pull remote branch

```git checkout --track origin/branch_to_pull```


Delete local and remote branch

```git push origin --delete branch_to_delete```


Show remote tags

```git ls-remote --tags origin```


Push new local branch to remote

```git push -u origin new_branch```


Show info about remote (eg. remote branches)

```git remote show origin```


Undo last local commit

```git reset --soft HEAD~1```


Revert remote commit(s). It will keep commits in local branch, but reset remote branch

```git push -f origin last_known_good_commit:branch_name```


Show what will be removed

```git clean -fgn```


Remove untracked files and directories

```git clean -fg```


Show differences between branches

```git diff master..branch-x```
```--name-status --name-only```


Show branch last update

```git for-each-ref --sort=committerdate refs/heads/ --format='%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(color:red)%(objectname:short)%(color:reset) - %(contents:subject) - %(authorname) (%(color:green)%(committerdate:relative)%(color:reset))'```


Show missing commits on master

```git log --cherry master...feature1```


Show changes history for a file

```git log --follow --patch .\README.md```


Show commits with contain specified text in the content of commited files

```git log -Gtest```  #show added/removed/modified text, 'test' is consider as regexp always
```git log -Stest```  #show added/removed text

Show commits touching lines in file (lines 10-15 in file.txt)

```git log -L10,15:path/to/file.txt```

Tagging

```git tag -a v1.1 f59a39e -m "Message details..."```
```git push --tags origin master```

Fetching all remote branches (Windows!)

```foreach ($r in %{git branch -r}) { %{git branch --track $r.Replace("origin/","").Trim() $r.Trim()} }```
```git fetch --all```
```git pull --all```

Show stash content

```git stash show -p stash@{1}```

Consider tracked file as unchanged 

```git update-index --assume-unchanged file```

Consider file as changed (reverse of above command)

```git update-index --no-assume-unchanged file```


