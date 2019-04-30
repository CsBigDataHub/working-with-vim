---
title: Nav Marks
parent: 1497
template: page-tut.php
order: 9
---

# Navigation Marks

<span class="sidenote">See `:help marks`</span> Navigation marks allow you to mark spots in your buffer and jump back and forth between marks. This is useful if you find yourself moving around a buffer, say for table of contents, imports, or constructor.

Navigation marks can be labeled using a single letter [a-z]

`ma`
: mark spot label it a

<code>\`a</code> or `'a`
: jump to spot labeled a


## Automatic Marks

Vim automatically creates some marks:

<code>\`\`</code> or `''`
: jump back to previous position

<code>\`.</code> or `'.`
: jump to last spot edited

Use `:marks` command to see all available marks.

<span class="tip">💡</span>You can mark spots in different files by using capital letter, and jump back and forth. Vim will even open the file if it is closed. See video in [Buffer section](/working-with-vim/buffers/).
