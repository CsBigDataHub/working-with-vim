---
title: Lines
parent: 1497
template: page-tut.php
order: 6
---

# Working with Lines

The line is a common object to work with when editing that Vim has numerous built-in functions and features to operate specifically on lines.


## Copy / Delete Lines

Two shortcuts exist for copying and deleting the current line.

Use `dd` to delete, and `yy` to copy the current line.

This is the same as using the `_` motion, so `dd` is equivalent to `d_`, however they are common enough actions that the shortcuts make it easier.

You can paste a deleted or yanked line elsewhere, use `p` to paste.

## Misc Line Commands

Here are a few other useful commands for working with lines.

`0`
: Go to first column

`^`
: Go to first printable character

`$`
: Go to end of line

`g_`
: Go to last printable character

`D`
: Delete from cursor to end of line

`I`
: Enter INSERT mode at start of line

`A`
: Enter INSERT mode at end of line

`:32` or `32G`
: Go to line number 32

`gg`
: Go to first line in buffer

`G`
: Go to last line in buffer


## Merge lines

Use `J` to merge lines together. If you press `J` with nothing highlighted, it will remove the current line ending and white-space bringing the next line up. If multiple lines are highlighted, pressing `J` will merge them all into a single line.

## Wrap Lines at Length

Use `gq` to wrap lines to a specified length defined by `textwidth`. If the `textwidth` option is not set the default is 79. I use this daily in commit messages to fit within 80 characters. To use, just highlight the lines you want and then type `gq`


## Improve Wrapped Line Navigation

Navigating up and down on a wrapped line can sometimes be weird in vim, since it skips over what looks like a second line, but really is the same. This is particularly helpful when using vim to write documentation or other text, like blog posts.

Add the following to your `.vimrc`

```vim
" move updown by visual (wrapped) lines
noremap j gj
noremap k gk
```

See [Configuration section](/working-with-vim/configuration/) for more on working with your vim config.

## Bubble Up Lines

Move a single or multiple lines up and down using control + arrow keys. The multiline one is a bit complex that I picked up somewhere.

```vim
" Bubble single lines
nmap <C-Up> :m .-2<CR>
nmap <C-Down> :m  .+1<CR>

" Bubble multiple lines
vnoremap <silent> <C-Up>  @='"zxk"zP`[V`]'<CR>
vnoremap <silent> <C-Down>  @='"zx"zp`[V`]'<CR>
```

