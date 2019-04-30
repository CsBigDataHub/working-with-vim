---
title: Configuration
parent: 1497
template: page-tut.php
order: 16
---

# Vimrc

You probably already know about `.vimrc` or if you use Neovim `.config/nvim/init.vim`. It is where you can put your configuration and shortcuts.  I'm going to include several examples from my config to give you an idea of what you can do.

<span class="sidenote">Use vim, vim is great!</span> You can check out my [.vimrc in my dotfiles](https://github.com/mkaz/dotfiles/blob/master/rcfiles/.vimrc). I've used Neovim in the past and it is a great project encouraging development in Vim. I didn't really notice any real difference between using either.

I don't recommend just copying and pasting mine or anyone's vim config. Most config is just one person's preferences, especially for shortcuts. The important part is to be able to read and understand what shortcuts and features they are implementing, and see if that can improve your workflow.

Your muscle memory may want settings or mappings to use a different set of keys; learning how it works allows you to shape vim to fit you.


## Leader

First, the `<Leader>` is a special key intended to be used for user definitions. So any setting of it will not conflict with other default vim commands. By default the leader key is `\` but it is common to map it to `,` which I do. Set leader character using:

```vim
let mapleader=","
```

## Create Your Own Commands

Here is a shortcut I use to open my config file using `:Edrc` command. User defined commands must start with a capital letter to distinguish from built-in commands.

```vim
" edit config file
command Edrc edit $MYVIMRC
```

## Mapping

You can map a set of key commands to another set. This allows you to create a simpler shortcut for a more complex set of keys. Mapping is modal, you need to tell vim what MODE you want the mapping to work.

Use `map` for normal and visual modes, `nmap` for mapping to work in just NORMAL mode, and use `vmap` for mapping to work in just VISUAL mode.

<span class="sidenote">See `:help map-commands` for additional commands for less common modes.</span>

A mapping entry consists of `[map-mode] {lhs} {rhs}` which simply stands for left and right hand sides.

The mapping translates what you typed on the left-hand side to the mapped keys on the right-hand side. The right-hand side is just a set of keys you might of typed.

It is a good best practice to use `noremap` instead of just `map` which means to not allow recursive remaping of the `{rhs}` of to avoid potential issues with other definitions or plugins.

Here is an example mapping to add a semi-colon to the end of the current line.

```vim
noremap <Leader>; g_a;<Esc>
```

The command `g_` moves to the last non-whitespace character on the line. The `a` puts you in insert mode after the cursor. `;` adds the semi-colon. `<Esc>` returns to NORMAL mode.

The mapping duplicates what you would type in the editor. With the mapping set in my .vimrc, to add a semi-colon on end of line I simply type `,;` in normal mode.

### Instant Quotes

An example mapping to wrap a word in single or double quotes.

```vim
" Surround with Quote
map <Leader>' ysiw'
map <Leader>" ysiw"
```

### Toggle Whitespace

An example mapping to toggle visible whitespace.

```vim
" toggle show whitespace
noremap <F3> :set list!<CR>
```

## Make me a Sandwich

My one great tip from my configuration, which I give credit to whoever I picked it up from years ago, this saves me so many times.


```vim
" :w!! to save with sudo
ca w!! w !sudo tee >/dev/null "%"
```

When you open a file and don't have write permissions, you can call `:w!!` and it will auto sudo the file for you. Saves me practically every time I edit a system file. [Sandwich reference](https://xkcd.com/149/)


## Auto Command

`Autocmd` is a powerful tool to configure vim to automatically run on a specific event. See `:help autocmd-events` for a listing of available events.

Here is a common usage, setting a parameter based on the type of file. In this case, I want PHP files to use tabs and not spaces, because that is the WordPress standard.

```vim
" PHP File Types (WordPress, use tabs)
autocmd FileType php set noexpandtab
```

If your vim config is sourced after loading, the autocmds will repeat and can double up the actions. It is recommended you use `augroup` to group together your set of autocmds in a block. By running `autocmd!` in that block it removes previous set commands.

Here is a simplified example from my config


```vim
augroup configgroup

    autocmd! " delete existing autocmds in group

    " golang
    autocmd BufRead,BufNewFile *.go set filetype=go
    autocmd FileType go nmap <Leader>r <Plug>(go-run)
    autocmd FileType go nmap <Leader>b :terminal go build<CR>
    autocmd FileType go nmap <Leader>t :terminal go test<CR>

augroup END
```
