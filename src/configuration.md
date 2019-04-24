---
title: Configuration
date: 2019-03-17
---

# Vimrc

You probably already know about `.vimrc` or `.config/nvim/init.vim` if you use neovim. It is where you can put your configuration and shortcuts.  I'm going to include several examples from my config to give you an idea of what you can do.

You can check out my <a href="https://github.com/mkaz/dotfiles/blob/master/extras/nvim/init.vim">.vimrc in my dotfiles</a> repo. I actually use neovim, so it is init.vim. I don't really recommend just copying and pasting the whole thing, it ends up being personal preferences anyways.

#### Edit Config File

A shortcut to open my config file using `:Edrc` command. User defined commands must start with a capital letter to distinguish from built-in commands.

```
" edit config file
command Edrc edit ~/.config/nvim/init.vim
```


## Leader

First, the `<Leader>` is a special key intended to be used for user definitions. So any setting of it will not conflict with other default vim commands. By default the leader key is `\` but it is common to map it to `,` which I do. Set leader character using:

```vim
let mapleader=","
```

## Mapping

You can map a set of keys to any action, to create a mapping you need to define what mode you want the mapping to work. Use `map` for normal and visual modes, `nmap` for just normal mode, and `vmap` for just visual mode.

<span class="sidenote">See `:help map-commands` for additional commands for less common modes.</span>

A mapping entry consists of `[map-mode] {lhs} {rhs}` which simply stands for left and right hand sides.

The mapping translates what you typed on the left-hand side to the mapped keys on the right-hand side. The right-hand side is just a set of keys you might of typed.

It is a good best practice to use `noremap` which means to not allow recursive remaping of the `{rhs}` of to avoid potential issues with other definitions or plugins.

Here is an example mapping to add a semi-colon to the end of the current line.

```vim
noremap <Leader>; g_a;<Esc>
```

The command `g_` moves to the last non-whitespace character on the line. The `a` puts you in insert mode after the cursor. `;` adds the semi-colon. `<Esc>` returns to NORMAL mode.

So the mapping simply duplicates what you would type in the editor. Now it is simplified so I can do all that just by typing `,;`

### Instant Quotes

An example using mapping to wrap a word in single or double quotes.

```
" Surround with Quote
map <Leader>' ysiw'
map <Leader>" ysiw"
```

--- TODO: animated gif wrapping word ---


## Plugin Management

I do recommend using <a href="https://github.com/junegunn/vim-plug">vim-plug</a> to manage plugins, it makes it easy to install, upgrade, and remove.

## Colorschemes

Since everyone asks, I use <a href="https://sourcefoundry.org/hack/">Hack font</a>, <a href="https://github.com/mhartington/oceanic-next">Oceanic Next</a> colorscheme, and <a href="https://github.com/vim-airline/vim-airline">Airline</a> for the fancy status bar.


## Make me a Sandwich

My one great tip from my configuration, which I give credit to whoever I picked it up from years ago, this saves me so many times.


```vim
" :w!! to save with sudo
ca w!! w !sudo tee >/dev/null "%"
```

When you open a file and don't have write permissions, you can call `:w!!` and it will auto sudo the file for you. Saves me practically every time I edit a system file.


## Auto Command

`Autocmd` is a powerful tool to configure vim to automatically run on a specific event. See `:help autocmd-events` for a listing of available events.

Here is a common usage, setting a parameter based on the type of file. In this case, I want PHP files to use tabs and not spaces, because that is the WordPress standard.

```
" PHP File Types (WordPress, use tabs)
autocmd FileType php set noexpandtab
```

