
### Config related
----

List all aliases

`git config --get-regexp alias`

### Branch related
----

#### Deleting:

Delete a local branch

* `git branch -d <branch name>`

Delete a remote branch

* `git push origin --delete <branchName>` (As of Git v1.7.0)
    * alternative: `git push origin :<branchName>` (Added in Git v1.5.0)

Remove obsolete tracking branches

* `git fetch --all --prune`

[Srouce](http://stackoverflow.com/a/2003515/6664582)