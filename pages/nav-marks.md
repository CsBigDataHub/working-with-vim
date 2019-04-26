---
title: Nav Marks
parent: 1430
template: page-tut.php
order: 9
---

# Navigation Marks

<span class="sidenote">See `:help marks`</span>
Navigation marks allow you to mark spots in your buffer and jump back and forth between marks. This is useful if you find yourself moving around a buffer, say for table of contents, imports, or constructor.

```vim
ma       " mark spot label it a
`a       " jump to spot labeled a
```

Vim automatically creates some marks:

```vim
``       " jump back to previous position
`.       " jump to last spot edited
```

Use `:marks` command to see all available marks.

<span class="tip">💡</span>You can mark spots in different files by using capital letter, and jump back and forth. Vim will even open the file in a buffer if closed. See buffer video below for an example.
