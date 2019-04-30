---
title: Basic Actions
parent: 1497
template: page-tut.php
order: 5
---

# Basic Actions

Here are a some basic actions, combine with [motions](/working-with-vim/basic-motions/) to define and perform action:

`y`
: Yank (copy)

`d`
: Delete

`p`
: Put (paste)


## Undo / Redo

Use `u` for undo, and `ctrl-r` for redo. No motion required, just press the keys.


## Uppercase & Lowercase

Use `gu{motion}` for lowercase, use `gU{motion}` for uppercase, or use `g~{motion}` to toggle case. So `guiw` will switch the current word to lowercase, or `g~_` will toggle the case of each character on the current line.


## Indent

<span class="sidenote">See `:help shift-left-right`</span> The brackets `<` and `>` will shift the line one `shiftwidth` length to the left, or right. These can also be paired with VISUAL mode, ranges, and motions.

For example, use `shift-v` to select a line, use arrows or other motions to expand the range, and then type `<` or `>` to shift the lines.

Use `<<` and `>>` to shift using a count. For example `5>>` will shift 5 lines once to the right. If you want to shift more use `.` to repeat the command.


## Formatting

The `=` command will automatically format text based on internal formatting rules for the language, or as defined by a plugin. The typical way I use is highlight the section I want using VISUAL mode and then pressing `=` to format.


## Repeat That

Press `.` to repeat the last command.

If you start with a number and then command it executes the command that many times. For example, if you want to delete three lines, `3dd`

<figure class="wp-block-video">
<video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-quickies.mp4"></video><figcaption>Quickies example</figcaption></figure>


