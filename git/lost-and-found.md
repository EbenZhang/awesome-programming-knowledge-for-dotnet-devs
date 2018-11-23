# Lost and Found

Whenever the HEAD \(the current commit\) changes, git will create a reflog. We can get it as long as the changes were commited.

To access the reflog, we go to the `Commands` menu and select the `Show reflog` menu item.

In the form we can see where the HEAD used to point to. Sometimes it's hard to tell which is the one we want, unfortunately there is not preview of the commit but we can create branches for couple of the HEADs and then go back to the main revision grid. We can do a `Hard` to the commit once we find it.

Commandline:

```text
git reflog -n # where n is the number of log items to show
git reset --hard <TheCommitSHA>
```

