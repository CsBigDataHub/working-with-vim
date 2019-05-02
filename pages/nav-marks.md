---
title: Nav Marks
parent: 1497
template: page-tut.php
order: 9
---

# Navigation Marks

<span class="sidenote">See `:help marks`</span> Navigation marks allow you to mark spots in your buffer and jump back and forth between marks. This is useful if you find yourself moving around a buffer, say for table of contents, imports, or constructors.

Navigation marks can be labeled using a single letter [a-z]

`ma`
: mark spot label it `a`

<code>\`a</code> or `'a`
: jump to spot labeled a

`:marks`
See all available marks.

The lowercase navigation marks [a-z] are remembered as long as the file remains in buffer list. If you remove the file, or the line that contains a mark, that mark is erased.

## File Marks

Use capital letters [A-Z] as file marks that allows you to jump to different files. Vim will even open the file if it is closed.File marks are stored in ~/.viminfo and will persist between sessions. See example in the video in [Buffer section](/working-with-vim/buffers/).

## Automatic Marks

Vim automatically creates some marks:

<code>\`\`</code> or `''`
: jump back to previous position

<code>\`.</code> or `'.`
: jump to last spot edited

