---
title: Text Objects
date: 2019-05-07
order: 7
---

# Text Object Selection

<span class="sidenote">See `:help text-object`</span> Vim can operate on text based on its objects and structure. The inner object `i` is quite useful to select chunks of text inside parentheses, brackets, quotes, tags and other pairs, use `a` to also select the delimiters.

An example might help illustrate. To select text inside an html tag you can use the tag text object `t`. With your cursor between the tags, use `v` to enter visual mode, `i` for inner, `t` for tag. So `vit` will select interior content between two tags. Use `vat` to select content with tags.

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/05/vim-tag-select.mp4"></video> <figcaption> Using tag selection </figcaption> </figure> 

## Selection Commands

`(`
: Parentheses

`{`  `[`  `>`
: Brackets

`'`  `"`  <code>`</code>
: Quotes and Ticks

`t`
: Tag block

`w`
: Words

`s`
: Sentences

`p`
: Paragraphs


Combine the text objects with operators. For example, to copy the arguments in a function use `yi(`

If you want delete a block of code in a `{ ... }` with your cursor inside the block, type `di{`

For text in quotes, type `yi"` to copy the word without the quotes. If you want copy to include the quotes use `a` instead of `i`.

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-selection.mp4"></video><figcaption>Selection example</figcaption></figure>

<span class="tip">💡</span> Use the inner selection motion with the cursor in the middle of a word, sentence, or paragraph to select the full object, without having to first navigate to the start.

