---
title: Modes
parent: 1430
template: page-tut.php
order: 1
---

# Modes

Vim is a modal editor, this simply means it has different modes of operations. The main modes are NORMAL, INSERT, and VISUAL mode.
<span class="sidenote">I capitalize the modes because vim does, I'm not shouting them.</span>

## NORMAL Mode

First up, I don't really like telling people what to do, no vim shaming here. I use arrow keys. Use arrows keys. They are great keys with labels and everything. I do have one recommendation, <strong>make NORMAL mode your default mode</strong>. I mash the Esc key about hundred times a minute. Every time I finish a sentence. Escape. There is a reason it is called NORMAL mode, it is the mode where you can do everything fancy.

INSERT mode is just typing text, any editor can do that.

Be NORMAL.


## VISUAL Mode

<span class="sidenote">When I use a capital letter, you use a capital letter. Capital. Capital.</span>

You can highlight multiple lines using `V`.  Press `V` in NORMAL mode, and the whole line will be highlighted and you will be in VISUAL mode, as you move up or down it will highlight other lines.

The `shift-v`, aka capital V, is VISUAL LINE mode, selecting whole lines at once.

If you type `ctrl-v` it is VISUAL BLOCK mode, it selects by characters. Press `ctrl-v` and move around to select things, try left or right movements to see by character. You can also use `ctrl-v` to do fancy multi-cursor things, see video example below.

Psst, don't tell the purists, but if you `set mouse=a` you can use your mouse to highlight things too.

VISUAL mode is pretty powerful, I use it frequently since it provides feedback seeing what is selected, and then unselected after the action.

<figure><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/visual-mode-exs.mp4"></video><figcaption>Visual Mode example</figcaption>
</figure>

<span class="tip">💡</span>After performing an action in VISUAL MODE the selection is no longer highlighted. Use `gv` to automatically reselect the area previously highlighted.

