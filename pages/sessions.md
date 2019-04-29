---
title: Sessions
parent: 1430
template: page-tut.php
order: 18
---

# Sessions

Vim stores the current state of views, window positions, and settings in a session. You can save the session to a file and load it at a later time to return vim to the same saved state.

## Create and Use Sessions

Use the command `:mksession [file]` to save the current state to a file, by default vim will use `Session.vim` filename if none specified.

Load a saved session using: `vim -S [file]`

## Plugin obsession.vim

Working with sessions can be a little tedious. You need to remember to update saving your state anytime you open a new file, or change the window layouts. I use the [obsession.vim](https://github.com/tpope/vim-obsession) plugin to help manage sessions.

The plugin manages keeping the state updated and will automatically save on quit. You simply run `:Obsess [file]` to start, if you don't specify a filename it will use `Session.vim` by default.

The state will be managed for you. After you exit vim, you load the sessiont the same using: `vim -S Session.vim`

## Startify

I use the [Startify plugin](https://github.com/mhinz/vim-startify) which replaces the empty start screen with a fancy one that includes a listing of recent files.  <span class="sidenote">With startify, you also get a quoting cow.</span> Startify will also detect if a `Session.vim` file exists and you can quick open it. This is nice when you forget to load it on the command-line. This is my preferred way to work.


Startify does have session features itself; allowing you to create and list multiple sessions. See [Startify documentation](https://github.com/mhinz/vim-startify/wiki/Plugin-features-in-detail#easy-session-handling) for more and see which way you prefer.


<span class="tip">💡</span> I add `Session.vim` to my global `.gitignore` file so it doesn't show in git commands and I don't have to add it to each project.
