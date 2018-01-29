# Bash Shortcuts

## Editing Commands

 * `Alt + f`: (or press `ESC` and release it and then press `f`): Forward (right) one word
 * `Alt + b`: (or press `ESC` and release it and then press `b`): Back (left) one word
 * `Ctrl + u`: Cut/delete the Line before the cursor to the clipboard
 * `Ctrl + k`: Cut the Line after the cursor to the clipboard
 * `Ctrl + w`: Cut the Word before the cursor to the clipboard
 * `Alt + d`: Delete the Word after the cursor
 * `Alt + Del`: Delete the Word before the cursor.
 * `Ctrl + y`: Paste the last thing that was cut

<!--more-->

## History Commands

 * `Ctrl + r`: Recall the last command including the specified character(s) searches the command history as you type
 * `Ctrl + p`: Previous command in the search result of `Ctrl + r`
 * `Ctrl + n`: Next command in the search result of `Ctrl + r`
 * `Alt + .` or `!$`: Reuse the last argument of previous command
 * `!*`: All arguments of previous command
 * `!!`: Repeat previous command
 * `!blah`: Run last/most recent command that starts with `blah`
 * `!blah:p`: Print last command starting with `blah`    
 * `^blah`: Delete `blah` from previous command
 * `^blah^foo`: Replace `blah` with `foo` in previous command

 To retain history across sessions the command history among sessions, you need to add the `PROMPT_COMMAND='history -a ~/.bash_history'` to your `.bash_profile`
 ```
 echo "PROMPT_COMMAND='history -a ~/.bash_history'" >> ~/.bash_profile
 . ~/.bash_profile # execute the profile to make it effect for opening bash session. Or reopen all bash sessions.
 ```