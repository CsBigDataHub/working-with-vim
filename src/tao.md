---
title: The Tao of Vim
date: 2019-03-02
---

# The Tao of Vim

The underlying principle of Vim is the action-motion pair. You perform an action on a subject, that is defined by the motion. For example, delete a line.

You can create action-motion pairs basically in two ways.

## NORMAL Mode

First, in NORMAL mode, you specify the action first and then the motion. Like the delete to beginning of the line example above. You type `d` for delete action and then `^` as the motion for beginning of the line.

If I just type `^` with no action, the cursor moves to the beginning of the line. Move is the default action.

## VISUAL Mode

The second way of defining a pair is VISUAL mode, except you do the opposite. You specify the noun (motion) part first by highlighting, and then perform the action on what is highlighted.

For example, type `gg` to move to the top of the file. `shift-v` to enter VISUAL LINE Mode and then `G` will move to end of file selecting all the lines. With the subject highlighted, you can use `d`or `y` to delete or copy.

I do this all the time to copy from one buffer to another. There might be a shortcut, but then I would need to remember it as a shortcut. Knowing how to highlight and move is less to remember, since it is the base of knowledge.

Note: You can perform this same action without using VISUAL mode by using `ggyG` but I tend to highlight. By selecting, I can see what is happening, what part highlighted and then get feedback when the action is performed.
