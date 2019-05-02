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

`nmap` or `nnoremap`
: just normal mode

`imap` or `inoremap`
: insert mode

`vmap` or `vnoremap`
: visual and select mode

`xmap` or `xnoremap`
: just visual mode

`cmap` or `cnoremap`
: command-line mode

`tmap` or `tnoremap`
: terminal mode

`map` or `noremap`
: normal, visual, and select modes


A mapping entry consists of `[map-mode] {lhs} {rhs}` which simply stands for left and right hand sides.

The mapping translates what you typed on the left-hand side to the mapped keys on the right-hand side. The right-hand side is just a set of keys you might of typed.

It is a good best practice to use the `noremap` version to not allow recursive remapping of the `{rhs}`. This avoids potential issues with other definitions or plugins.

It is also recommended to use `xmap` instead of `vmap` for VISUAL mode, unless there is a specifc reason to need the mapping also in select mode.

Here is an example mapping for NORMAL mode to add a semi-colon to the end of the current line.

```vim
nnoremap <Leader>; g_a;<Esc>
```

The `nnoremap` specifies the mapping for NORMAL mode, non-recursive. The next part is the command to type `<Leader>;` which for my leader defintion is `,;` The next part is the command you would type to achieve the results.

In this case `g_` moves to the last non-whitespace character on the line. The `a` enters INSERT mode after the cursor, and `;` adds the semi-colon. Finally, I add `<Esc>` to return to NORMAL mode.

A mapping just duplicates what you would type in the editor. With that mapping line set in my `.vimrc`, all I need to do to add a semi-colon on end of line is type `,;` in NORMAL mode.

### Instant Quotes

An example mapping to wrap a word in single or double quotes. This uses the [vim-surround plugin](https://github.com/tpope/vim-surround) an example that needs to be recursive.

```vim
" Surround with Quote
nmap <Leader>' ysiw'
nmap <Leader>" ysiw"
```

### Toggle Whitespace

An example mapping to toggle visible whitespace, the `!` is used as a toggle.

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
