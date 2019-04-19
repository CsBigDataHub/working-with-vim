---
title: Lines
date: 2019-03-06
---

## Merge lines

Use `J` to merge lines together. If you press `J` with nothing highlighted, it will remove the current line ending and white-space bringing the next line up. If multiple lines are highlighted, pressing `J` will merge them all into a single line.

## Wrap Lines at Length

Use `gq` to wrap lines to a specified length defined by `textwidth`. If the `textwidth` option is not set the default is 79. I use this daily in commit messages to fit within 80 characters. To use, just highlight the lines you want and then type `gq`


## Improve Wrapped Line Navigation

Navigating up and down on a wrapped line can sometimes be weird in vim, since it skips over what looks like a second line, but really is the same. This is particularly helpful when using vim to write documentation or other text, like blog posts.

```
" move updown by visual (wrapped) lines
map j gj
map k gk
```

-- TODO: animated gif navigating line ---

## Bubble Up Lines

Move a single or multiple lines up and down using control + arrow keys. The multiline one is a bit complex that I picked up somewhere.

```
" Bubble single lines
nmap <C-Up> :m .-2<CR>
nmap <C-Down> :m  .+1<CR>

" Bubble multiple lines
vnoremap <silent> <C-Up>  @='"zxk"zP`[V`]'<CR>
vnoremap <silent> <C-Down>  @='"zx"zp`[V`]'<CR>
```
