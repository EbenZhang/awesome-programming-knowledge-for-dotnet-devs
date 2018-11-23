# How to Compare Commits or Branches

If the commit are close in the graph, we can select one and select another with CTRL key press. Then we can see the diff in the diff view.

If they are far away, we can right click one commit/branch and select the `Compare` menu

![CompareBranchMenu.png](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/CompareBranchMenu.png)

In the branch/commit compare form you can swap the BASE and the HEAD, or compare to merge base, or even select another commit to compare. Unfortunately it doesn't have a files filter right now.

Commandline

```text
git diff <branchA>..</branchb>  # also works for commits
git diff <branchA>...</branchb> # compare to merge base.
```

#### Merge Base

```text
         o---o---o---o---o---o---o---B
        /
---o---merge base is here---o---o---o---A
```

