---
title: Text Objects
parent: 1430
template: page-tut.php
order: 7
---

# Text Object Selection

<span class="sidenote">See `:help text-object`</span>
Vim can operate on text based on its objects and structure. The inner object `i` is quite useful to select chunks of text inside parentheses, brackets, quotes, or other pairs.

For example, to copy the arguments in a function use `yi(`

If you want delete a block of code in a `{ ... }` with your cursor inside the block, type `di{`

This also works for text in quotes, if you typed `yi"` it will copy the word without the quotes. If you want copy to include the quotes use `a` instead of `i`, this works for all the examples above.

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-selection.mp4"></video><figcaption>Selection example</figcaption></figure>

<strong>Extra</strong>: The inner selection motions work with words `w`, sentences `s`, and paragraphs `p`. So if the cursor is in the middle of a word, sentence, or paragraph you can use `i` paired with the motion and it will select the full object. This is so you don't need to first navigate to the start of a word to select the whole word.
