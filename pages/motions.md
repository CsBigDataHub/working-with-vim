---
title: Basic Motions
parent: 1497
template: page-tut.php
order: 4
---

# Basic Motions

Here are a few of the most common motions, there are many more and plugins can define there own but it is good to start learning the basics and expand.

`w`
: Forward to next word

`b`
: Backward to start of word

`e`
: Forward to end of word

`gg`
: Top of file

`G`
: Bottom of file

`fx`
: Forward to 'x'

`Fx`
: Backward to 'x'

`_`
: Current line (underscore)

Practice the basic motions by just pressing the motion character, while in NORMAL mode, the cursor will move. So pressing `w` moves the cursor forward to the next word.

If you put an action first, it will perform that action on the motion. For example `dw` it will delete to the next word, including the space.

If you start with `v` it will highlight based on the motion in VISUAL mode, so `ve` will highlight to the end of the word.

<span class="tip">💡</span> If you `p` paste with something highlighted, it will replace the highlighted section. This is extremely helpful, since deleting an item can change what is in your register you are trying to paste. See [Registers](/working-with-vim/registers/) for more.

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/copy-vis-paste.mp4"></video></figure>
