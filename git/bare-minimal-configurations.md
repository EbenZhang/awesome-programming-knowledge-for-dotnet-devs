# Bare Minimal Configurations

Here are the bare minimal configurations, your GitExtensions might look different but similar. It's recommended to select the `Global for all repositories` so that we don't have to configure our repositories individually.

![](../.gitbook/assets/image%20%281%29.png)



* Username and email are straightforward.
* Editor is mainly used for interactive rebase which we will discuss later. We can choose the `"C:\Program Files (x86)\GitExtensions\GitExtensions.exe" fileeditor` from the dropdown to use the GitExtensions' built-in editor or whatever we like except `notepad` \(until the line ending issue is fixed by Microsoft\).
* Mergetool is mainly used when solving merge conflicts, make sure you choose one that supports 3-way merge such as BeyondCompare, KDiff, Meld. After put in the `Path to mergetool`, we can use the `Suggest` button to fill the `Mergetool command`
* Difftool is used to compare diff in your favourite external tool
* Line ending: If you only develop on Windows you can choose the `Checkout Windows-style`, otherwise better to use the `as-is`

For the difftool and mergetool, we could also modify the `~/.gitconfig` file to have something like below \(for BeyondCompare3\)

```text
[diff]
        guitool = beyondcompare3
        tool = BeyondCompare3
        indentHeuristic = true
[merge]
        tool = BeyondCompare3
[mergetool "BeyondCompare3"]
        path = C:/Program Files (x86)/Beyond Compare 3/bcomp.exe
        cmd = \"C:/Program Files (x86)/Beyond Compare 3/bcomp.exe\" \"$LOCAL\" \"$REMOTE\" \"$BASE\" \"$MERGED\"
[difftool "beyondcompare3"]
        path = C:/Program Files (x86)/Beyond Compare 3/bcomp.exe
        cmd = \"C:/Program Files (x86)/Beyond Compare 3/bcomp.exe\" \"$LOCAL\" \"$REMOTE\"
```



