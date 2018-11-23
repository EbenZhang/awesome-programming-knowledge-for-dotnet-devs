# Rewrite History

Changing the published commits is a bad practice as it will mess the history of other developers. Usually they will see both our old and new commits hence confused. Their old branches on top of the old commits will need to rebase on top of the new commits too.

However, rewriting history is the key to clean up our own branch that has not been published. We can amend commits, reword commits, squash commits and even get rid of one of them.

Tips: although you can get back your commits using `reflog`, creating a backup branch before rebasing can help you get back your original branch/commits in case anything wrong during rebase. Moreover, you can easily compare your rebased commits with the original ones. BTW, when creating the backup branch, you can untick the `Checkout after create` so as to stay on the original branch.

#### How to amend the commit message of the last commit

See [https://git-extensions-documentation.readthedocs.io/en/latest/modify\_history.html\#modify-the-last-commit](https://git-extensions-documentation.readthedocs.io/en/latest/modify_history.html#modify-the-last-commit)

Tick the Amend Commit checkbox, give it a new message and commit without staging any changes.![Amend Last Commit Message](https://camo.githubusercontent.com/7d33ae52be13927945bf6b5429c1c9e93a9e5747/68747470733a2f2f6769742d657874656e73696f6e732d646f63756d656e746174696f6e2e72656164746865646f63732e696f2f656e2f6c61746573742f5f696d616765732f616d656e645f636f6d6d69742e706e67)

commandline:

```text
git commit --amend
```

#### How to reword commit message

Interactive rebase needed to change the commit message for commits in middle like:

![Commits in Middle](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/CommitsInMiddle.png)

In this case, we right click the parent commit `my awesome changes` and select the interactive rebase menu.

![Rebase Interactively](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/RebaseInteractively.png)

Git then will popup the Editor with the content like below \(the commits show in reverse order, the last is the most recent commit\).

```text
pick d310b7c35 WIP: Fix blah blah
pick f3ee84093 WIP: Continue Fix blah blah
pick 07ec28ec2 Fix another stupid bug
```

We now change the `pick` to `r` or `reword` \(Unfortunately, we can't change the commit message here directly\) and save and close the Editor.

```text
r d310b7c35 WIP: Fix blah blah
r f3ee84093 WIP: Continue Fix blah blah
pick 07ec28ec2 Fix another stupid bug
```

Git will popup the Editor again asking for the new commit message for the first commit. Now put the new message and close the Editor and do the same thing for the second commit.

Commandline:

```text
git rebase -i HEAD~3 
# or the parent commit SHA if it's hard to count
git rebase -i <TheParentCommitSHA>
```

Note: there is also an Reword commit menu somewhere in GitExtensions but it is recommended that you use the interactive rebase to get yourself familar with what happened behind the scenes.

#### How to edit the last commit

If not all the changes should go into the commit, we can do a `Mixed` reset to the previous commit and redo the commit with only the wanted changes.

![Reset to previous commit](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/ResetMenu.png)

commandline

```text
git reset HEAD~
# add only the wanted file 
# or use interactive add to add some portions of the file
git add awesome_changes.txt 
git commit
```

If more changes to be added to the commit, similar to how we amend the message of the last commit, we can stage the additional changes, then tick the Amend Commit checkbox and commit it.

Command line

```text
git add awesome_changes.txt
git commit --amend
```

#### How to squash last few commits

If just want to squash last few commits we can do a `Mixed` or `Soft` reset to their parent commit and recommit the changes.

Note: with `Mixed` reset, we have to stage the files again, whereas `Soft` will keep the files in staging area.

For example, in below image, we want to squash the last two commits `WIP: Continue Fix blah blah` and `WIP: Fix blahblah`. We can right click their parent commit `my awesome changes`, select the `Reset current branch to here`, then select the `Mixed:xxx` option.

![Squash LastFew Commits](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/SquashLastFewCommits.png)

Commmandline:

```text
git reset HEAD~2
git add <the files> # or use git add -a to add all files to staging area
git commit
```

#### How to squash commits in middle

Similar to how we reword commits in middle. We start an interactive rebase, but this time instead of `reword`, we change the `pick` to `s` or `squash` for the second commit meaning squash the second up into the first commit.

```text
pick d310b7c35 WIP: Fix blah blah
s f3ee84093 WIP: Continue Fix blah blah
pick 07ec28ec2 Fix another stupid bug
```

After saved and closed the Editor, Git then will popup the Editor asking for the new commit message of the squashed commits.

```text
# This is a combination of 2 commits.
# This is the 1st commit message:

WIP: Fix blah blah

# This is the commit message #1:

WIP: Continue Fix blah blah

```

We now need to replace the `WIP: Fix blah blah` with a new commit message `Fix blahblah`and remove the `WIP: Continue Fix blah blah`.

Once finished it looks like below \(I created a `before_rebase` branch so we can see it more clearly\):

![After Squash](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/AfterSquash.png)

The `fixup` option: `fixup` is very similar to `squash` except that `fixup` uses the commit message of the first commit whereas `squash` requires a new commit message.

#### How to split one commit into multiple

Let's say we want to split the `WIP: Fix blah blah` into multiple commits. We again right click the parent commit `my awesome changes` and start an interactive rebase.

This time we change the `pick` to `e` or `edit`

```text
e d310b7c35 WIP: Fix blah blah
pick f3ee84093 WIP: Continue Fix blah blah
pick 07ec28ec2 Fix another stupid bug
```

After saved and closed, the GitExtensions may stop at the Rebase Dialog \(which is not very friendly\), we can safely close it.

![InMiddleOfRebaseDialog.png](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/InMiddleOfRebaseDialog.png)

Then it goes back to the main revision grid looks like below, also notice the message at the bottom right `You are in middle of a rebase`:

![BeforeEditCommit.png](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/BeforeEditCommit.png)

Now we can do a `Mixed` reset to the parent commit `my awesome changes`, and commit as many commits as we want. Once finished, click the bottom right `You are in middle of a rebase`message and press the `Continue` button to continue the rebase.

Note: there is also an Edit commit menu somewhere in GitExtensions but it is recommended that you use the interactive rebase to get yourself familar with it.

#### How to push after rewriting history

If we've previously pushed the branch, the server will reject our push after rewriting history, which can be forced with `--force-with-lease`.

![PushDialog.png](https://github.com/EbenZhang/gitextensions/raw/Beta/PracticalGitImages/PushDialog.png)

**Important**:

Before using the commandline version of force push such as `git push --force-with-lease` or `git push --force`, you should make sure the `push default` setting is not `match`. When it's `match` git will push all your local branches that matches the branches on the remote server thus extremely dangerous when combined with `force`

```text
# to get the value from the global settings
# assuming it.s global as very likely you won't configure it per project
git config --global --get push.default
# to set the value to nothing
git config --global push.default nothing
```

See [https://git-scm.com/docs/git-config\#git-config-pushdefault](https://git-scm.com/docs/git-config#git-config-pushdefault) for other options

#### What is the difference between force-with-lease and force push

Force with lease is a little bit safer than force as it checks if the remote branch at local PC is the same as the branch at the remote server, for example, the push of `awesome_branch` to GitHub \(let's say we are using GitHub\) will fail if the local `origin/awesome_branch` at our side is different to the `awesome_branch` on GitHub \(Someone else may have pushed something to the branch, but we haven't fetch the commits\).

