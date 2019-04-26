---
title: Substitute
parent: 1430
template: page-tut.php
order: 10
---

# Substitute

<span class="sidenote">See `:help substitute`</span> Substitute allows you to search and replace using regular expressions. The command `s/find/replace/g` will replace "find" with "replace", the `s` is for substitute, the `g` (global) option replaces every occurrence in a line, without the `g` it will only replace the first occurrence in a line.

Prefix the command with the range to work on, if no range is specified it will only search and replace on the current line.


<span class="sidenote">The space between range and `s` is not necessary, but I find it more legible.</span>

Use `%` to search and replace across the whole document. `:% s/find/replace/g`

Specify a line number range using `:137,140 s/find/replace/g` will replace all "find" with "replace" between lines 137 and 140.

You can also define the range using VISUAL mode. First highlight the area you want and then type `:` to go into command-line mode. Vim will automatically insert `'<,'>` which is its magical incantation to work over the selection, leave it there, and type your substitute command `s/find/replace`

Besides search and replace, you can use `g/find/d` to delete all lines that match find, or `v/find/d` to delete all lines that do not match find.

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-search.mp4"></video><figcaption>Search examples</figcaption></figure>

