---
title: Buffers
parent: 1497
template: page-tut.php
order: 13
---

# Buffers

Buffers in vim are the in-memory text of files. Your window is a viewport on a buffer. You can switch between open buffers, which works similar in concept to tabs in other editors. Vim does have a concept of tabs too, but they are slightly different, read more about tabs in the [Windows section](/working-with-vim/windows/).

I generally keep it pretty simple and just use buffers. They handle my multiple files open at the same time needs. Don't take just my view, here is a post about [Buffers vs Tabs](https://joshldavis.com/2014/04/05/vim-tab-madness-buffers-vs-tabs/), and the author agrees just using buffers is easier.

My main reason is if you specify multiple files on the command-line, or use `:ed FILE` to open additional files, they are opened in extra buffers. Buffers seem to be the default mode, so it is what I learned and use.

## Main Buffer Commands

`:buffers` or `:ls`
: Show open buffers

`:bd`
: Close current buffer

`:bn`
: Switch to Next buffer

`:bp`
: Switch to Previous buffer in list

`:b#`
: Last buffer visited, actual # sign

`:b1`
: Open buffer 1

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-buf-mark.mp4"></video><figcaption>Buffers example</figcaption></figure>

## Buffer Navigation

To make buffer navigation easier, I map `<Leader>3` to jump back to last buffer, this makes it easy to bounce between two files.

I map `<Leader>n` to navigate to next buffer, I map `Q` to close current buffer, and map `;`  to open the buffer list to select a buffer.

Here is what the mappings look like in my `.vimrc`, see [configuration section](/working-with-vim/configuration) for more about mapping and leader.

```vim
" Buffer Navigation
nnoremap <Leader>3 :b#<CR>    " previous buffer
nnoremap <Leader>n :bn<CR>    " next buffer
nnoremap Q :bd!<CR>           " close buffer
nnoremap ; :Buffers<CR>       " browse buffers
```

The `:Buffers` command above is slightly different and comes from the [fzf.vim plugin](https://github.com/junegunn/fzf.vim). See my article [Unix is my IDE](https://mkaz.blog/code/unix-is-my-ide/) for an explanation on how I setup vim using fzf and ripgrep for advanced searching, which includes this quick way to switch buffers using fzf.

