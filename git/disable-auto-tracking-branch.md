# Disable Auto Tracking Branch

With GitExtensions, when pushing a branch the target branch name is usually defaulted to be the same as the branch being pushed. But with tracking branch enabled, the target branch might be the old branch if it was renamed from another one and as a result we may push the changes to the old branch.

Run the following command to disable Auto Tracking Branch:

```text
git config --global branch.autosetupmerge false
```

and edit the file in you `.git/config` to remove the trackings.

for example, deleting the `merge = refs/heads/master` for `awesome_branch` will stop the tracking.

```text
[branch "awesome_branch"]
    remote = origin
    merge = refs/heads/master
```

