# Useful git commands #

## Branching ##

Fetch information about remote branches

```git fetch origin```


Pull remote branch

```git checkout --track origin/branch_to_pull```


Delete local and remote branch

```git push origin --delete branch_to_delete```
```git branch -d branch_to_delete```

Push new local branch to remote

```git push -u origin new_branch```


Show info about remote (eg. remote branches)

```git remote show origin```


Fetching all remote branches (Windows PowerShell!)

```
foreach ($r in %{git branch -r}) { %{git branch --track $r.Replace("origin/","").Trim() $r.Trim()} }

git fetch --all # fetches remote branches 

git pull --all # update local branches which track remote branches
```

Show branch last update

```git for-each-ref --sort=committerdate refs/heads/ --format='%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(color:red)%(objectname:short)%(color:reset) - %(contents:subject) - %(authorname) (%(color:green)%(committerdate:relative)%(color:reset))'```

## Commiting ##

Undo last local commit

```git reset --soft HEAD~1```

Revert remote commit(s). It will keep commits in local branch, but reset remote branch

```git push -f origin last_known_good_commit:branch_name```

Commit part of the file

```git add <filename> -p -i```

## Merging ##

Merge feature branch commits as one commit in master branch

```
git checkout master

git merge --squash feature-branch

git commit -m ....
```

## Cleaning ##

Show what will be removed

```git clean -fn```

Remove untracked files and directories

```git clean -f```

## Rebasing ##

Remove 'n' commits from branch

```git rebase --onto <branch name>~<first commit number to remove> <branch name>~<first commit to be kept> <branch name>```

## Diff ##

Show differences between branches

```git diff master..branch-x```
```--name-status --name-only```


Show missing commits on master

```git log --cherry master...feature1```


Show changes history for a file

```git log --follow --patch .\README.md```

Show commits with contain specified text in the content of commited files

```git log -Gtest```  #show added/removed/modified text, 'test' is consider as regexp always
```git log -Stest```  #show added/removed text

Show commits touching lines in file (lines 10-15 in file.txt)

```git log -L10,15:path/to/file.txt```

## Tagging ##

```
git tag -a v1.1 f59a39e -m "Message details..."

git push v1.1 origin

git tag -d v1.1

git push origin :refs/tags/v1.1
```

Show remote tags

```git ls-remote --tags origin```

## Stashing ## 

Show stash content

```
git stash show -p stash

git stash show -p stash@{1}
```

## File tracking ##

Consider tracked file as unchanged 

```git update-index --assume-unchanged file```

Consider file as changed (reverse of above command)

```git update-index --no-assume-unchanged file```

## SSL ##

Skipping SSL certificate check

```git config --global http.sslVerify false```


