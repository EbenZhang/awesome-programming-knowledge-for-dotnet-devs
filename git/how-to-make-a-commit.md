# How to Make a Commit

There are two steps to commit our changes. First, we decide which files/lines to be in the commit by staging them. Second, we give the commit a message to commit.

![StageAndCommit](https://camo.githubusercontent.com/423dd7c7b778cdc7856b6f2053c624220e8f1228/68747470733a2f2f6769742d657874656e73696f6e732d646f63756d656e746174696f6e2e72656164746865646f63732e696f2f656e2f6c61746573742f5f696d616765732f636f6d6d69745f6469616c6f672e706e67)

Note: Unlike other source control management systems, git optimisitically allows us change files without locking it \(it is a distributed source control management system and therefore never knows or cares who is changing a file on another computer\).

Command line:

```text
git add awesome_changes.txt # add the file to staging area
git commit
```

#### Logic commit

A commit should be

* a wrapper for related changes. Fixing different issues should produce separate commits. Otherwise it's hard to review and to understand the intention when someone needs to change the code
* in a buildable status as sometimes you or other developers may want to check the commit out \(bisect\) and build the application to make sure a defect was not introduced by the commit.

In order to make logic commit, we should commit often whenever we can, otherwise it might be hard to split at the end when we finished all the changes. Moreover, committing often can help us get back the changes/commit after an accidentally reset or deletion of some new files.

It's OK to have some Work In Progress commits before we publish our branch, but make sure it's only for ourselves and they are cleaned up before going public.

#### How to write a git commit message

The commit message has two parts, the summary and the details separating by a blank line. The summary should describe WHAT was the intention of the commit and the details can explain more about the WHY and HOW. GitHub shows the subject as the commit message and the details as three dots, which we can click to see the details.

When writing the commit message, we should focus on the WHAT and WHY, not the HOW. Here are some bad ones:

* `Update SQL Script`: what was fixed?
* `Change X from 3 to 2`: what was fixed? Why 3 didn't work?
* `Review comments fixed`: this should only be used for trivial changes such as renaming a variable, fixing a typo. A separate commit is needed for any significant changes.
* `Fix issue #1234`: oops, the issue is no longer there because the team migrated away from one issue management system to another.

> One story goes that Beth wanted to cook a pot roast according to an award-winning pot roast recipe handed down in her husband's family. Her husband, Abdul, said that his mother had taught him to sprinkle it with salt and pepper, cut both ends off, put it in the pan, cover it, and cook it. Beth asked, "Why do you cut both ends off?" Adbul said, "I don't know. I've always done it that way. Let me ask my mother." He called her, and she said, "I don't know. I've always done it that way. Let me ask your grandmother." She called his grandmother, who said, "I don't know why you do it that way. I did it that way becuase it was too big to fit in my pan." – Quoted from &lt;&lt;Code Complete 2nd edition&gt;&gt; Page 53

**Git Commit Message Template**

See examples at [https://github.com/torvalds/linux/commits/master](https://github.com/torvalds/linux/commits/master)

```text
WHAT was solved/implemented in this commit

More details about the symptoms and the cause of the issue
If we can found out, describe why the original change was made
Describe the reason why this change was made
If there is another alternative, describe why we didn't choose it
```

Basically, we focus on the WHAT and WHY instead of the HOW since we can easily figure out the SQL script was updated from the changes made.

### How to add only a portion of a file

In the commit dialog, we do not have to commit all of the changes of a file. In the diff view on the right, we can select individual lines for the next commit, and press the \[S\] key or the Stage context menu item to add the lines to the staging area.

You may want to turn the `ignore white space` options off which can be located at the dock bar on the right top of the diff view when the view is focused.

Commandline:

```text
git add -i
# or
git add --interactive
```

