---
title: Modes
parent: 1497
template: page-tut.php
order: 1
---

# Modes

Vim is a modal editor, this simply means it has different modes of operations. The main modes are NORMAL, INSERT, and VISUAL mode. <span class="sidenote">I capitalize the modes because vim does, I'm not shouting them.</span> Commands are based on what mode you are in, the majority are used while in NORMAL mode.

## NORMAL Mode

First up, I don't really like telling people what to do, no vim shaming here. I use arrow keys. Use arrows keys. They are great keys with labels and everything. I do have one recommendation, <strong>make NORMAL mode your default mode</strong>. I mash the Esc key often to constantly return to NORMAL mode. Every time I finish an edit I hit Esc.

There is a reason it is called NORMAL mode, it is the mode where you can do all the extra vimmy stuff. INSERT mode is just typing text, any editor can do that.

Be NORMAL.


## VISUAL Mode

`v`
: Enter VISUAL mode (character)

`V`
: Enter VISUAL LINE mode (line)

`ctrl-v v`
: Enter VISUAL BLOCK mode (column)


Press `v` in NORMAL mode to enter VISUAL mode. In VISUAL mode any cursor movement, or defined motion will select text as it moves. You can operate on just this highlighted area.

Press `V` in NORMAL mode, and the whole line is selected, this is VISUAL LINE mode. Any movement up or down will select by line.

Press `ctrl-v` for VISUAL BLOCK mode. Moving will select by a block region, not the entire line. This allows for operating on columns of text, see video example below.

Psst, don't tell the purists, but if you `set mouse=a` you can use your mouse to highlight things too.

VISUAL mode is pretty powerful, I use it frequently since it provides feedback seeing what is selected, and then unselected after the action.

<figure><video controls src="https://mkaz.blog/wp-content/uploads/2019/05/vim-visual-mode.mp4"></video><figcaption>VISUAL Mode example</figcaption>
</figure>

<span class="tip">💡</span>After performing an operation in VISUAL MODE the selection is no longer highlighted. Use `gv` to automatically reselect the area previously highlighted.

## Command-line Mode

Another mode to mention is Command-line mode. You enter by typing `:` while in NORMAL or VISUAL mode. This places your cursor at the bottom command-line, ready for you to type a command.

Typically you exit command-line mode by issuing a command, however you can exit without a command by typing `Esc Esc`

A history of previous commands is kept, use the up arrow key after typing `:` to see previous commands, similar to bash. This is stored in `.viminfo` so persists between sessions.

