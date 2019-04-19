---
title: Actions II
date: 2019-03-16
---

## Misc Actions

Once you get a handle on the motions, then it is a matter of learning additional actions to pair with them. Here are a couple of useful actions.


### Uppercase &amp; Lowercase

Use `gu{motion}` for lowercase, use `gU{motion}` for uppercase, or use `g~{motion}` to toggle case. So `guiw` will switch the current word to lowercase, or `g~_` will toggle the case of each character on the current line.


### Indent

The brackets `&gt;` and `&lt;` will shift the line one `shiftwidth` length to the right, or left. These can also be paired with VISUAL mode , ranges, and motions.

For example, use `shift-v` to select a line, use arrows or other motions to expand the range, and then type `&gt;` or `&lt;` to shift the lines.

Use `&gt;&gt;` and `&lt;&lt;` to shift using a count. For example `5&gt;&gt;` will shift 5 lines once to the right. If you want to shift more use `.` to repeat the command.

See `:help shift-left-right`

### Formatting

The `=` command will automatically format text based on internal formatting rules for the language, or as defined by a plugin. The typical way I use is highlight the section I want using VISUAL mode and then pressing `=` to format.
