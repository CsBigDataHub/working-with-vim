---
title: Operators
date: 2019-05-05
order: 5
---

# Operators

Here are some basic operators, these are combined with [motions](/working-with-vim/basic-motions/) to edit text:

`y`
: Yank (copy)

`d`
: Delete

`p`
: Put (paste)

`c`
: Change, deletes and enters INSERT mode

<span class="tip">💡</span> Use `p` paste with something highlighted to replace the highlighted section. This is extremely helpful, since deleting an item can change what is in your register you are trying to paste. See [Registers](/working-with-vim/registers/) for more.

<figure><asciinema-player src="/working-with-vim/casts/copy-paste.cast" font-size="large" cols="58" rows="15"></asciinema-player><figcaption>Copy-Paste example</figcaption></figure>

## Undo / Redo

Use `u` for undo, and `ctrl-r` for redo. No motion required, just press the keys in NORMAL or VISUAL mode.


## Uppercase & Lowercase

`gu{motion}`
: Lowercase test

`gU{motion}`
: Uppercase text

`g~{motion}`
: Toggle text case

For example, `gu_` will switch the current line to lowercase, or `g~_` will toggle the case of each character on the current line.


## Indent

<span class="sidenote">See `:help shift-left-right`</span> The brackets `<` and `>` will shift the line one `shiftwidth` length to the left, or right. These can also be paired with VISUAL mode, ranges, and motions.

For example, use `shift-v` to select a line, use arrows or other motions to expand the range, and then type `<` or `>` to shift the lines.

Use `<<` and `>>` to shift using a count. For example, `5>>` will shift 5 lines once to the right. If you want to shift more use `.` to repeat the command.


### Formatting

<span class="sidenote">See `:help =` </span> The `=` command will indent text based on internal formatting rules, or as defined by a plugin for the language. The typical way I use is to highlight the section I want to format using VISUAL mode, and then press `=` to format.


## Repeat That

Press `.` to repeat the last command.

If you start with a number, and then type a command, Vim executes the command that many times. For example, if you want to delete three lines, type `3dd`

## Single Character Operators

`rX`
: Replace character under cursor with `X`

`x`
: Delete character under cursor

`~`
: Toggle case for character under cursor


