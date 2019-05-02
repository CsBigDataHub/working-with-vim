---
title: Modes
parent: 1497
template: page-tut.php
order: 1
---

# Modes

Vim is a modal editor, this simply means it has different modes of operations. The main modes are NORMAL, INSERT, and VISUAL mode.
<span class="sidenote">I capitalize the modes because vim does, I'm not shouting them.</span>

## NORMAL Mode

First up, I don't really like telling people what to do, no vim shaming here. I use arrow keys. Use arrows keys. They are great keys with labels and everything. I do have one recommendation, <strong>make NORMAL mode your default mode</strong>. I mash the Esc key often to constantly return to NORMAL mode. Every time I finish an edit I hit Esc.

There is a reason it is called NORMAL mode, it is the mode where you can do all the extra vim stuff. INSERT mode is just typing text, any editor can do that.

Be NORMAL.


## VISUAL Mode

You can highlight multiple lines using `V`.  Press `V` in NORMAL mode, and the whole line will be highlighted and you will be in VISUAL mode, as you move up or down it will highlight other lines.

<span class="sidenote">When I use a capital letter, you use a capital letter. Capital. Capital.</span>

The `shift-v`, aka capital V, is VISUAL LINE mode, selecting whole lines at once.

If you type `ctrl-v` it is VISUAL BLOCK mode, it selects by characters.

Press `ctrl-v` and move around to select things, try left or right movements to see by character. You can also use `ctrl-v` to do fancy multi-cursor things, see video example below.

Psst, don't tell the purists, but if you `set mouse=a` you can use your mouse to highlight things too.

VISUAL mode is pretty powerful, I use it frequently since it provides feedback seeing what is selected, and then unselected after the action.

<figure><video controls src="https://mkaz.blog/wp-content/uploads/2019/05/vim-visual-mode.mp4"></video><figcaption>VISUAL Mode example</figcaption>
</figure>

<span class="tip">💡</span>After performing an action in VISUAL MODE the selection is no longer highlighted. Use `gv` to automatically reselect the area previously highlighted.

## Command-line Mode

One other mode to mention is Command-line mode. You enter this mode by typing `:` while in NORMAL or VISUAL mode. This places your cursor at the bottom of the screen, on the single command-line, ready for you to type the command.

The majority of ways to exit command-line mode is issuing a command, however you can exit without typing a command by typing `Esc Esc`

Command-line also maintains a history of previous commands, after typing `:` use the up arrow key, similar to bash, to see previous commands.

