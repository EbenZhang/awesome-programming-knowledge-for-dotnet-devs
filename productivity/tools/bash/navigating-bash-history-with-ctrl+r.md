# Navigating Bash History with Ctrl+R

Bash \(and Git Bash\) records the history of all the commands you have typed and puts it in `~/.bash_history`. It is really useful to look back at the history to use the same commands again or edit them slightly. You can press the up arrow to go through your history but it can take a really long time to find what you're looking for. So instead, try `Ctrl + r`.

To do this: first press `Ctrl + r`, then start typing the command or any part of the command that you are looking for. You'll see an autocomplete of a past command at your prompt. If you keep typing, you'll get more specific options appear. You can also press `Ctrl + r` again as many times as you want to, this goes back in your history to the previous matching command each time.

Once you see a command you like, you can either run it by pressing return, or start editing it by pressing arrows or other movement keys.

To retain history across sessions, you need to add the `PROMPT_COMMAND='history -a ~/.bash_history'` to your `.bash_profile` then close and reopen all bash sessions

```text
 echo "PROMPT_COMMAND='history -a ~/.bash_history'" >> ~/.bash_profile
```

