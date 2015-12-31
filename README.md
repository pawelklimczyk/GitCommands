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

Show waht will be removed

```git clean -fgn```

Remove untracked files and directories

```git clean -fg```

