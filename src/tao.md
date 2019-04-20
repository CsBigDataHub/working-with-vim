---
title: The Tao of Vim
date: 2019-03-02
---

# The Tao of Vim

The underlying principle of Vim is the action-motion pair. You perform an action on a subject, that is defined by a motion. For example, delete a line.

You can create action-motion pairs basically in two ways.

## NORMAL Mode

First, in NORMAL mode, you specify the action first and then the motion. For example, delete to beginning of the line. You type `d` for delete action and then `^` as the motion to the beginning of the line.

If you type `^` with no action, the cursor moves to the beginning of the line. Move is the default action, so if a motion is specified with no action the cursor will move.

## VISUAL Mode

The second way of defining a pair is in VISUAL mode, you do the opposite. You specify the motion part first by selecting, and then perform the action on what is highlighted.

For example, type `ctrl-v` to enter VISUAL mode, then type `^` as the motion to the beginning of the line, then type `d` to delete.

This is obviously an extra step to select the text, but VISUAL mode shows you what is highlighted and being acted upon. Additionally, there is feedback when the action is complete since the selection will no longer be highlighted.

<span class="sidenote">Copy buffer in NORMAL mode using `ggyG`, but I prefer selecting. I see what is highlighted and get feedback when the yank action is performed.</span>

I find the feedback useful, particularly when copying.

For example, copying a whole buffer using VISUAL mode: Type `gg` to move to the top of the file. `shift-v` to enter VISUAL LINE Mode and then `G` will move to end of file selecting all the lines. With the subject highlighted, use `y` to copy.


