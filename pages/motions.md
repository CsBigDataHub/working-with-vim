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

`fx`
: Forward to 'x' (cursor on char)

`Fx`
: Backward to 'x' (cursor on char)

`tx`
: Forward to 'x' (cursor before char)

`Tx`
: Backward to 'x' (cursor before char)

`;`
: Repeat previous motion works with `f F t T`

`_`
: Current line (underscore)

Practice the basic motions by just pressing the motion character(s), while in NORMAL mode the cursor will move. So pressing `w` moves the cursor forward to the next word. You can precede any motion with a number, for example `5w` will move forward to the fifth next word.

When you put an action first, it will perform that action on the motion. For example `dw` will delete to the next word, this includes the space, not just the word.

<span class="tip">💡</span> There are minor differences between `w` and `e`; as well as between `f` and `t`. The differences are around where the cursor ends up, this can make a big difference depending on the action. For example, `dfx` will delete forward up to and including the `x` character, whereas `dtx` will delete up to but not including the `x`.

You can visualize the motions by starting with `v` and then the motion, it will highlight the selected area. See the difference between `ve` highlighting to the end of the word, to `vw` highlighting to the next word.

## Window Motions

Here are a set of less commonly used window motions. They can be quite useful to quickly jump to different sections of the visible window. See help on each for exact definition and options.

`H`
: High, jump to top of window

`M`
: Middle, jump to middle of window

`L`
: Low, jump to bottom of window

`zz`
: Window is centered on line, cursor does not jump
