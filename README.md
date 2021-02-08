# Useful git commands #


| Command(s) | Description |
|---|---|
|git fetch origin|Fetch information about remote branches|
|git checkout --track origin/branch_to_pull|Pull remote branch|
|git push origin --delete branch_to_delete|Delete remote branch|
|git branch -d branch_to_delete|Delete local branch|
|git branch branch_name sha1_of_the_commit|Create branch from commit|
|git push -u origin new_branch|Push new local branch to remote|
| git branch -m old-name new-name; git push origin :old-name new-name; git push origin -u new-name|Rename local and remote branch|
|git remote show origin|Show info about remote (eg. remote branches)|
|foreach ($r in %{git branch -r}) { %{git branch --track $r.Replace("origin/","").Trim() $r.Trim()} } & git fetch --all & git pull --all |Fetching all remote branches (Windows PowerShell!)|
|git for-each-ref --sort=committerdate refs/heads/ --format='%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(color:red)%(objectname:short)%(color:reset) - %(contents:subject) - %(authorname) (%(color:green)%(committerdate:relative)%(color:reset))'|Show branch last update|
|git reset --soft HEAD~1|Undo last local commit|
|git push -f origin last_known_good_commit:branch_name|Revert remote commit(s). It will keep commits in local branch, but reset remote branch|
|git add <filename> -p -i|Commit part of the file|
|git checkout master & git merge --squash feature-branch & git commit -m xxx|Merge feature branch commits as one commit in master branch|
|git clean -fn|Show what will be removed|
|git clean -f|Remove untracked files and directories|
|git rebase --onto <branch name>~<first commit number to remove> <branch name>~<first commit to be kept> <branch name>|Remove 'n' commits from branch|
|git diff master..branch-x OR --name-status --name-only|Show differences between branches|
|git log --cherry master...feature1|Show missing commits on master|
|git log --follow --patch .\README.md|Show changes history for a file|
|git log -Gtest```  #show added/removed/modified text, 'test' is consider as regexp always|Show commits with contain specified text in the content of commited files|
|git log -Stest  #show added/removed text|Show commits with contain specified text in the content of commited files|
|git log -L10,15:path/to/file.txt|Show commits touching lines in file (lines 10-15 in file.txt)|
|git tag -a v1.1 f59a39e -m "Message details..."|Add tag|
|git push v1.1 origin|Push tag|
|git ls-remote --tags origin|Show remote tags|
|git tag -d <tag>|Remove local tag|
|git push origin --delete <tag> |Remove remote tag|
|git stash show -p stash OR git stash show -p stash@{1}|Show stash content|
|git update-index --assume-unchanged file|Consider tracked file as unchanged|
|git update-index --no-assume-unchanged file|Consider file as changed (reverse of above command)|
|git config --global http.sslVerify false|Skipping SSL certificate check|

## Copy repository to new location ##

```
git remote rename origin old-origin

git remote add origin git@gitgub.com:your-new-repo/repo.git

git push -u origin --all

git push -u origin --tags
```
