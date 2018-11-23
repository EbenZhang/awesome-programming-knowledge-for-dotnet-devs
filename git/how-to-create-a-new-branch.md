# How to Create a New Branch

See [https://git-extensions-documentation.readthedocs.io/en/latest/branches.html\#create-branch](https://git-extensions-documentation.readthedocs.io/en/latest/branches.html#create-branch)

![GitExtensionsCreateBranch](https://camo.githubusercontent.com/d875230775c5fe41fd147dcf3651c24cc2a60b3d/68747470733a2f2f6769742d657874656e73696f6e732d646f63756d656e746174696f6e2e72656164746865646f63732e696f2f656e2f6c61746573742f5f696d616765732f6e65775f6272616e63682e706e67)

Commandline

```text
git checkout -b <BranchName> [origin/<RemoteBranchName>]

git checkout -b <BranchName> [CommitOrRef]

git branch <BranchName> [CommitOrRef]
```

#### Create on top of remote branch instead of local

Most of time we'd like to create our branch basing on the remote branch for example `origin/master`, instead of a local `master`. A local `master` branch is only needed when we want to push something directly to the remote `master`. If commits are meant to be merged through pull requests, we can delete it to avoid inadvertently push to the remote `master` branch.

#### Fetch before creating

Most of time we'd like to fetch the remote branch first before creating branch, because the `origin/master` on our PC might not be up to date as the branch on remote server.

#### Fetch & Create in one go

In the left branch tree panel, find the remote branch, right click and select the menu `Fetch & Checkout` if want to use the same name as the local branch name or `Fetch & Create Branch` if a different name needed.

![FetchAndCreate.png](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/FetchAndCreate.png)

